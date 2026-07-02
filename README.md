# Locker-EXE-Graduation

Umbrella repository for the **Smart Laundry Locker System** — FPT EXE graduation project.

This repo doesn't contain application code directly; it links the individual
sub-projects as git submodules so the whole system can be browsed/cloned from
one place, while each part is still developed and versioned independently.

## Sub-projects

| Submodule | Description | Visibility |
|---|---|---|
| [`laundry-locker-ai`](https://github.com/LDKhangg/laundry-locker-ai) | AI-assisted laundry locker service (Python) | Public |
| [`laundry-locker-frontend-admin`](https://github.com/LDKhangg/laundry-locker-frontend-admin) | Admin frontend (TypeScript) | Private — request access if needed |

## Clone with submodules

```bash
git clone --recurse-submodules https://github.com/LDKhangg/Locker-EXE-Graduation.git
```

Already cloned without `--recurse-submodules`?

```bash
git submodule update --init --recursive
```

## Staying in sync

A scheduled GitHub Actions workflow (`.github/workflows/update-submodules.yml`)
pulls the latest commit from each submodule's default branch and pushes an
update automatically, so this repo always points at the newest state of
`laundry-locker-ai` and `laundry-locker-frontend-admin` without manual work.

> Note: the workflow uses the default `GITHUB_TOKEN`, which can read the
> public `laundry-locker-ai` submodule but **cannot** access the private
> `laundry-locker-frontend-admin` submodule. To also auto-update that one,
> add a personal access token with `repo` scope as a repository secret named
> `SUBMODULE_PAT` (Settings → Secrets and variables → Actions) — the workflow
> will use it automatically if present.

To update manually instead:

```bash
git submodule update --remote --merge
git add .
git commit -m "chore: update submodules"
git push
```
