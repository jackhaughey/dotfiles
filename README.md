# Dotfiles — Managed with chezmoi

A reproducible, portable dotfiles setup built around **chezmoi**, **mise**, **starship**, and a collection of shell scripts for cloud tooling and Kubernetes workflows.  
Optimised for **Fedora Atomic desktops** (Silverblue/Kinoite/Sericea) and **containerised dev environments** (Toolbox, Distrobox, DevPod).

---

## Features

- chezmoi‑managed dotfiles for clean, reproducible configuration  
- Bash configuration with mise initialisation and quality‑of‑life aliases  
- Starship prompt preset installation  
- mise version manager bootstrapping + tool installation  
- Cloud tooling installer (AWS CLI, Azure CLI, kubectl, Helm, etc.)  
- Kubernetes helper script (`k8s.sh`)  
- Custom fonts under `~/.local/share/fonts`  
- Idempotent run‑once scripts for first‑time setup  

---

## Repository Structure
```
dotfiles/
├── chezmoi.toml
├── dot_bashrc
├── dot_config/
│   └── starship.toml
├── dot_local/
│   └── share/fonts/
├── k8s.sh
├── run_once_install_tools.sh.tmpl
├── run_once_setup_mise.sh.tmpl
├── run_once_starship_preset.sh.tmpl
├── run_once_20_cloud_tools.sh.tmpl
```

---

## Installation

### 1. Ensure Chezmoi is installed, as per the fedora-atomic-bootstrap repo
chezmoi is installed automatically when running:

fedora‑atomic‑bootstrap → bootstrap.sh

If you haven’t run it yet, start there:`


### 2. Apply dotfiles
```bash
chezmoi init jackhaughey
chezmoi apply
```
This will:

    Install fonts

    Configure bash

    Install mise + tools

    Apply starship preset

    Install cloud tooling

    Run all run_once_*.tmpl scripts

Key Components
Bash Configuration

.bashrc includes mise initialisation, PATH adjustments, aliases, and starship setup.
mise Setup

run_once_setup_mise.sh.tmpl installs mise and your defined tools.
Starship Prompt

run_once_starship_preset.sh.tmpl installs your preferred starship preset.
Cloud Tools

run_once_20_cloud_tools.sh.tmpl installs AWS CLI, Azure CLI, kubectl, Helm, and more.
Kubernetes Helpers

k8s.sh provides shortcuts and helper functions for cluster workflows.

---

## Updating Your Dotfiles
```bash
chezmoi add <file>
chezmoi apply
git commit -am "update"
git push
```

## Roadmap

    Add Nix bootstrap

    Add DevPod templates

    Add Toolbox/Distrobox presets

    Add GCP/OCI tooling
