# S²IL website

Static site for the Scalable Scientific Imaging Lab, built with [Zola](https://www.getzola.org/) and deployed to S3/CloudFront on pushes to `main`.

Live site: [https://s2il.org](https://s2il.org)

## Prerequisites

Install [Zola](https://www.getzola.org/) (0.23.x recommended). Verify with `zola --version`.

### macOS

```bash
brew install zola
```

### Linux

Download the latest Linux binary from the [GitHub releases](https://github.com/getzola/zola/releases) page (e.g. `zola-v0.23.6-x86_64-unknown-linux-gnu.tar.gz` or the aarch64 build for ARM). Then:

```bash
tar -xzf zola-v*-x86_64-unknown-linux-gnu.tar.gz
mkdir -p ~/.local/bin
mv zola ~/.local/bin/
# ensure ~/.local/bin is on your PATH, then:
zola --version
```

### Windows

**Winget:**

```powershell
winget install getzola.zola
```

**Scoop:**

```powershell
scoop install zola
```

**Chocolatey:**

```powershell
choco install zola
```

Zola does not work in PowerShell ISE; use Windows Terminal, PowerShell, or Command Prompt.

More options (including building from source): [Zola installation docs](https://www.getzola.org/documentation/getting-started/installation/).

## Local development

From the repo root:

```bash
zola serve
```

Open the URL printed in the terminal (default [http://127.0.0.1:1111](http://127.0.0.1:1111)). The site rebuilds automatically when you edit files under `content/`, `templates/`, `sass/`, or `static/`.

Useful options:

```bash
zola serve -O          # open in the default browser
zola build             # write a production build to public/
```

Content lives in Markdown under `content/` (projects, people, news, publications). Images and other assets go in `static/` (e.g. `static/images/…`).

## Publishing changes

Pushes to `main` trigger a GitHub Action that builds the site with Zola and syncs `public/` to S3, then invalidates the CloudFront cache.

```bash
git status
git add -A
git commit -m "Short description of the change"
git push origin main
```

Watch the workflow under the repo’s **Actions** tab. After it succeeds, allow a minute or two for CloudFront to refresh before checking [https://s2il.org](https://s2il.org).

### Required repository secrets

Configured under **Settings → Secrets and variables → Actions**:

| Secret | Purpose |
|--------|---------|
| `S3_BUCKET` | Destination bucket name |
| `AWS_ACCESS_KEY_ID` | IAM access key |
| `AWS_SECRET_ACCESS_KEY` | IAM secret key |
| `AWS_REGION` | e.g. `us-east-1` |
| `CLOUDFRONT_DISTRIBUTION_ID` | Distribution to invalidate after deploy |

`base_url` in `config.toml` should remain the production URL (`https://s2il.org`). In-page links are root-relative, so local `zola serve` stays on localhost.
