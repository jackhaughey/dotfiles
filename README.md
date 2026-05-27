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

---

## Installation

### 1. Install chezmoi

```bash
sh -c "$(curl -fsLS get.chezmoi.io)"
```

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


