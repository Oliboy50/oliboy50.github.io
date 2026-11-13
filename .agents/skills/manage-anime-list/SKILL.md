---
name: manage-anime-list
description: >-
  Add new animes or update existing anime entries (seasons, episodes, OAVs, movies, Blu-ray status, or rank) in animes.md using the imdb-search CLI tool. Use this skill whenever the user asks to add an anime, update seasons/episodes of an anime, or modify entries in animes.md.
---

# Manage Anime List (`animes.md`)

Use this skill when adding new animes to `animes.md` or updating existing entries (such as incrementing `number_of_seasons` and `number_of_episodes`).

## 1. Fetching Anime Metadata from IMDb

Use the globally linked `imdb-search` CLI tool (from `imdb-data-extractor`) to fetch the IMDb URL, poster `image_url`, demographic `genre`, release `year`, `number_of_episodes`, and `number_of_seasons`:

```bash
imdb-search "<Anime Title | IMDb URL | ttID>"
```

> Note: Because `imdb-search` queries IMDb's external APIs (`v3.sg.media-imdb.com` and `caching.graphql.imdb.com`), run it with `BypassSandbox: true` if sandboxed network access is blocked.

Example output from `imdb-search`:
```yaml
[1] https://www.imdb.com/title/tt0434706/
  - title: "Monster (2004, TV series)"
    image_url: https://m.media-amazon.com/images/M/MV5BYzU2MWQ5NGQtYmNlMC00ZjJkLWJmODItZDM5MDM3YmUyMWJkXkEyXkFqcGc@._V1_UX1000_.jpg
    imdb: https://www.imdb.com/title/tt0434706/
    genre: [seinen]
    year: 2004
    number_of_episodes: 75
    number_of_seasons: 1
```

## 2. Entry Schema in `animes.md`

Each entry in the `list:` frontmatter of `animes.md` must follow this exact structure and property order:

```yaml
  - title: <Title>
    image_url: https://m.media-amazon.com/images/M/<IMAGEID>._V1_UX1000_.jpg
    imdb: https://www.imdb.com/title/tt<ID>/
    genre: [<genres>]
    year: <YYYY>
    number_of_episodes: <total_episodes_watched>
    number_of_seasons: <total_seasons_watched> # Optional when only 1 season
    number_of_oavs: <count>                    # Optional
    number_of_movies: <count>                  # Optional
    bluray_bought: true                        # Optional
```

### Rules & Conventions
1. **`title`**:
   - The user will often provide an approximate or partial title; always infer the final `title` value from the official title returned by IMDb.
   - Strip the ` (YYYY, TV series)` suffix that `imdb-search` includes in its preview title.
   - If the user provides an alternate French/Japanese title in parentheses, format it as `Main Title (Alt Title)`.
   - Quote the title if it contains a colon (`:`), or double quote the title if it contains a single quote (`'`).
2. **`imdb`**:
   - Always use the canonical locale-neutral URL `https://www.imdb.com/title/ttXXXXXXX/` (without `/fr/`).
3. **`genre`**:
   - Must be a YAML inline array (`[...]`) containing one or more of the 5 allowed values:
     - `shonen` (for boys, e.g., *Naruto*, *Jujutsu Kaisen*)
     - `shojo` (for girls, e.g., *Fruits Basket*, *Nana*)
     - `seinen` (for men, e.g., *Monster*, *Berserk*)
     - `josei` (for women, e.g., *Chihayafuru*, *The Apothecary Diaries*)
     - `kodomuke` (for children, e.g., *Sherlock Holmes*, *Captain Tsubasa*)
   - An anime can belong to multiple genres (e.g., `genre: [shonen, seinen]` or `genre: [seinen, josei]`). Verify the inferred genre from `imdb-search` and include secondary demographic genres when appropriate.
4. **`year`**:
   - 4-digit integer release year (`YYYY`) of the anime series.
5. **Placement when adding**:
   - Unless the user specifies a rank/position in the list, append the new item at the end of the `list:` array in `animes.md` (immediately before the closing `---` of the frontmatter).

## 3. Updating Seasons & Episodes of an Existing Anime

When the user asks to update an existing anime (e.g., "add season 2 (12 episodes) to X" or "update X with the latest season"):
1. Search for the anime's `title` in `animes.md`.
2. Check whether the entry is a standard flat item or uses a nested `list:` of sub-series:
   - **Standard item**:
     - `number_of_episodes` stores the **cumulative total** of episodes across all watched seasons. Add the new season's episode count to the existing `number_of_episodes`.
     - Increment `number_of_seasons` (or add `number_of_seasons: 2` if it previously had 1 season and `number_of_seasons` was omitted).
     - If the user didn't specify the episode count of the new season, run `imdb-search` using the item's `imdb` URL or title to check the total episodes/seasons on IMDb.
   - **Nested `list:` item** (e.g., *Hunter x Hunter*, *Dragon Ball*, *Naruto*):
     - Update the relevant sub-item's `number_of_episodes` / `number_of_seasons` or add a new sub-item under `list:`.

## 4. Validation

After modifying `animes.md`, validate the YAML frontmatter in the sandbox:

```bash
ruby -E UTF-8 -ryaml -e '
content = File.read("animes.md")
parts = content.split(/^---\s*$/)
fm = YAML.safe_load(parts[1])
list = fm["list"]
allowed = %w[shonen shojo seinen josei kodomuke]
bad = list.select { |i|
  !i["title"] ||
  !i["image_url"]&.start_with?("https://m.media-amazon.com/") ||
  i["imdb"] !~ %r{\Ahttps://www\.imdb\.com/title/tt\d+/\z} ||
  !i["genre"].is_a?(Array) || i["genre"].empty? || (i["genre"] - allowed).any? ||
  !i["year"].is_a?(Integer)
}
abort("Validation failed for: #{bad.map { |i| i["title"] }}") if bad.any?
puts "Valid! Total animes: #{list.size}"
'
```
