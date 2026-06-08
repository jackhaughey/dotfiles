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
├── archive
│   ├── k8s.sh
│   ├── run_once_20_cloud_tools.sh.tmpl
│   ├── run_once_install_tools.sh.tmpl
│   └── run_once_setup_mise.sh.tmpl
├── chezmoi.toml
├── dot_bashrc
├── dot_config
│   ├── alacritty
│   │   └── alacritty.toml
│   ├── k9s
│   │   └── aliases.yaml
│   ├── shell
│   │   └── aliases.sh
│   └── starship.toml
├── dot_local
│   └── share
│       └── fonts
│           └── run_once_install_meslo_fonts.sh.tmpl
├── README.md
└── run_once_starship_preset.sh.tmpl
```

---

## Installation

### 1. Ensure Chezmoi is installed, as per the fedora-atomic-bootstrap repo
chezmoi is installed automatically when running:

fedora‑atomic‑bootstrap → bootstrap.sh

If you haven’t run it yet, start there:`


### 2. Apply dotfiles
```bash
chezmoi init --apply https://github.com/jackhaughey/dotfiles
```
This will:

    Install fonts

    Configure bash

    Apply starship preset

    Run all run_once_*.tmpl scripts

Key Components
Bash Configuration

Starship Prompt
run_once_starship_preset.sh.tmpl installs your preferred starship preset.

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
