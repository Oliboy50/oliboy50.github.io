# Oliver THEBAULT website

## Development

### Requirements

A recent [pages-gem](https://github.com/github/pages-gem) Docker image must be available on your computer:

```shell
git clone git@github.com:github/pages-gem.git
cd pages-gem
make image
cd ..
rm -rf pages-gem
```

### Run website locally

```shell
docker run -it --rm \
    -p 4000:4000 \
    -v $(pwd):/src/site \
    gh-pages jekyll clean
docker run -it --rm \
    -p 4000:4000 \
    -v $(pwd):/src/site \
    gh-pages jekyll serve --watch --force_polling -H 0.0.0.0 -P 4000
```
