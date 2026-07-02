<div align="center">

# 🔒 Locker-EXE-Graduation

**Smart Laundry Locker System** — FPT EXE graduation project.

</div>

This repo doesn't contain application code directly; it's an **umbrella
repository** that links every sub-project as a git submodule, organized by
layer, so the whole system can be browsed or cloned from one place while
each part is still developed and versioned independently in its own repo.

## 📁 Structure

```
Locker-EXE-Graduation/
├── backend/
│   └── laundry-locker-microservices/   Backend microservices
├── frontend/
│   ├── laundry-locker-frontend/        User-facing web app
│   └── laundry-locker-frontend-admin/  Admin dashboard
├── mobile/
│   └── smart-laundry-locker-mobile/    Mobile app
└── ai/
    └── laundry-locker-ai/              AI-assisted locker service
```

## 👥 Team & sub-projects

| Layer | Repo | Owner | Visibility |
|---|---|---|---|
| Backend | [`laundry-locker-microservices`](https://github.com/BaoHuy-Dev/laundry-locker-microservices) | [BaoHuy-Dev](https://github.com/BaoHuy-Dev) | Public |
| Frontend (user) | [`laundry-locker-frontend`](https://github.com/LeThiYenVi/laundry-locker-frontend) | [LeThiYenVi](https://github.com/LeThiYenVi) | Public |
| Frontend (admin) | [`laundry-locker-frontend-admin`](https://github.com/LDKhangg/laundry-locker-frontend-admin) | [LDKhangg](https://github.com/LDKhangg) | Private — request access if needed |
| Mobile | [`smart-laundry-locker-mobile`](https://github.com/BaoHuy-Dev/smart-laundry-locker-mobile) | [BaoHuy-Dev](https://github.com/BaoHuy-Dev) | Public |
| AI service | [`laundry-locker-ai`](https://github.com/LDKhangg/laundry-locker-ai) | [LDKhangg](https://github.com/LDKhangg) | Public |

## 🚀 Clone with submodules

```bash
git clone --recurse-submodules https://github.com/LDKhangg/Locker-EXE-Graduation.git
```

Already cloned without `--recurse-submodules`?

```bash
git submodule update --init --recursive
```

## 🔄 Staying in sync

A scheduled GitHub Actions workflow (`.github/workflows/update-submodules.yml`)
pulls the latest commit from every submodule's default branch and pushes an
update automatically, so this repo always points at the newest state of all
5 sub-projects without manual work.

> Note: the workflow uses the default `GITHUB_TOKEN`, which can read all the
> **public** submodules above but **cannot** access the private
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
