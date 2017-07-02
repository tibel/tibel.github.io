# tibel.github.io

This is my (experimental) personal website and blog.

## Notes

To run Jekyll on local machine using Docker:
```powershell
docker run --rm --label=jekyll --volume="$PWD":/srv/jekyll  -it -p 4000:4000 jekyll/minimal:pages jekyll serve --force_polling
```
