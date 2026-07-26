# tomergee-web

Personal site for [tomergee.com](https://tomergee.com). One static file, no build step.

- `index.html` — the landing page (name, tagline, link list). Edit it directly.
- `trip-*/index.html` — unlisted trip doc. Not linked from anywhere, served at an
  unguessable path, `noindex`ed and disallowed in `robots.txt`. Unlisted is not
  private: anyone with the URL can read it, and if this repo is public the file
  and its history are readable on GitHub regardless of the path.
- `robots.txt` — keeps crawlers off the unlisted pages.
- `CNAME` — custom domain for GitHub Pages.

## Local preview

Open `index.html` in a browser, or:

```sh
python3 -m http.server 8000
```

## Deploy (GitHub Pages)

1. Merge this branch into `main`.
2. Repo **Settings → Pages** → Source: *Deploy from a branch* → `main` / `/ (root)`.
3. Under **Custom domain**, enter `tomergee.com` and enable *Enforce HTTPS* once the
   certificate is issued.

## DNS at GoDaddy

In GoDaddy's DNS manager for `tomergee.com`:

| Type  | Name  | Value                 |
| ----- | ----- | --------------------- |
| A     | `@`   | `185.199.108.153`     |
| A     | `@`   | `185.199.109.153`     |
| A     | `@`   | `185.199.110.153`     |
| A     | `@`   | `185.199.111.153`     |
| CNAME | `www` | `tomergee.github.io.` |

Delete GoDaddy's default parking/forwarding records for `@` first, otherwise they
conflict. Propagation usually takes minutes but can take up to a day.
