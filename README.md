# tomergee-web

Personal site for [tomergee.com](https://tomergee.com). One static file, no build step.

- `index.html` — the whole site (name, tagline, three links). Edit it directly.
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
