# Local preview

GitHub Pages currently uses Ruby 3.3.4, Jekyll 3.10.0, and the
`github-pages` gem 232. Check https://pages.github.com/versions.json when
updating these versions.

The preview is not an exact GitHub Pages environment: transitive gem versions
and enabled plugins may differ.

From PowerShell in this directory, start a WSL container:

```powershell
wslc run --rm -p 127.0.0.1:4000:4000 --mount "type=bind,source=$((Get-Location).Path),target=/site" -w /site ruby:3.3.4 sh -c 'gem install github-pages -v 232 --no-document && gem install webrick --no-document && exec jekyll _3.10.0_ serve --host 0.0.0.0 --force_polling'
```

Open http://localhost:4000 and press Ctrl+C to stop. Gems are installed on
container startup. Docker or Podman can also run the image; bind-mount syntax
may vary.
