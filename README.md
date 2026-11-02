# Mahesh A Y — DevOps Portfolio

[![Build and Deploy](https://github.com/maheshay06/mahesh-portfolio/actions/workflows/hugo.yml/badge.svg)](https://github.com/maheshay06/mahesh-portfolio/actions/workflows/hugo.yml)

A static portfolio built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme. It covers my work in cloud infrastructure, container orchestration and automation. Pushing to `main` builds and deploys it to GitHub Pages.

**Deployments / login portal:** https://mahesh.svtv.tech/login

## About

B.E. Computer Science student (ACS College of Engineering, expected 2027) seeking a DevOps Engineering internship or full-time role.

- **Cloud:** AWS (EC2, S3, IAM), Microsoft Azure
- **Containers:** Kubernetes, Docker, Ingress, YAML manifests
- **IaC & automation:** Terraform, Ansible, Jenkins, CI/CD, Shell
- **Version control & OS:** Git/GitHub, Linux/Unix

## Tech stack

| Layer | Tool |
|---|---|
| Static site generator | Hugo (extended) |
| Theme | PaperMod (Git submodule) |
| CI/CD | GitHub Actions |
| Hosting | GitHub Pages |

## Project structure

```text
.
├── .github/workflows/hugo.yml   # build + deploy pipeline
├── content/
│   ├── _index.md                # homepage
│   ├── about.md                 # about + skills matrix
│   ├── achievements.md
│   └── projects/                # one Markdown file per project
├── static/resume.pdf            # served at /resume.pdf
├── themes/PaperMod              # theme (submodule)
└── hugo.toml                    # site config, menu, theme params
```

## Run locally

Requires Git and [Hugo extended](https://gohugo.io/installation/) v0.146 or later.

```bash
git clone --recurse-submodules https://github.com/maheshay06/mahesh-portfolio.git
cd mahesh-portfolio
hugo server -D
```

If you cloned without `--recurse-submodules`:

```bash
git submodule update --init --recursive
```

The site is served at http://localhost:1313/.

## Build

```bash
hugo --gc --minify
```

Output goes to `public/`.

## Add a project

```bash
hugo new content projects/my-project.md
```

Edit the front matter (`title`, `date`, `description`, `tags`), write the content, and remove `draft: true` when it's ready.

## Deployment

`.github/workflows/hugo.yml` runs on every push to `main`:

1. Installs Hugo extended.
2. Checks out the repo with the theme submodule.
3. Builds with `hugo --gc --minify`, using the Pages base URL.
4. Uploads the artifact and deploys it to GitHub Pages.

One-time setup: in the repo go to **Settings → Pages → Source: GitHub Actions**.

To update Hugo, change `HUGO_VERSION` in the workflow. To update the theme:

```bash
git submodule update --remote --merge themes/PaperMod
```

## Contact

- Email: maheshaychintu6@gmail.com
- LinkedIn: https://linkedin.com/in/aymahesh
- GitHub: https://github.com/maheshay06
