# 에이전틱 코딩 처음 시작하기 · Agentic Coding From Scratch

엔지니어가 되고 싶은 비엔지니어를 위해, 에이전틱 코딩에 필요한 소프트웨어 엔지니어링 기본기를 다시 정리한 소책자.

A booklet that re-organizes basic software engineering for agentic coding, for non-engineers who want to become engineers.

- [웹사이트에서 읽기 · Read on the website](https://keunwoopark.github.io/agentic-coding-from-scratch/)
- [한국어로 읽기](ko/README.md)
- [Read in English](en/README.md)
- [PDF (A5)](pdf/agentic-coding-from-scratch-ko.pdf) · [English PDF (A5)](pdf/agentic-coding-from-scratch-en.pdf)

## Repository layout

| Path | Contents |
|---|---|
| `ko/` | Korean text: `README.md` (preface), `chapter*.md`, `metadata.yaml`, `cover-text.tex` |
| `en/` | English text, same files as `ko/` |
| `book/` | print edition shared by all languages (see [book/README.md](book/README.md)) |
| `figures/` | TikZ sources of the diagrams, with text in every language |
| `img/<lang>/` | diagrams built from `figures/`, per language |
| `img/shared/` | screenshots used by every language |
| `pdf/` | reading PDFs (A5, with covers), built by `make pdf` |
| `site/` | website: page template, styles, pandoc filters (`make site`) |

Each language lives in its own folder with the same file names, so chapters
line up across languages. Build a language's print book with
`make book lang=<folder>` (default `ko`).

The website is built with `make site` (needs only pandoc) into `build/site/`
and published to GitHub Pages by `.github/workflows/pages.yml` on every push
to `main`. It serves every language folder plus `img/` and `pdf/`, so after
changing figures or text, rebuild and commit `make figures` / `make pdf`
for the site to pick them up.

The key colour is coral blue (`#2e9fd3`): `--accent` in `site/style.css` and
`bg` in `book/cover.tex`.
