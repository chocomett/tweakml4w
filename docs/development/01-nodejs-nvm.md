# 01. Node.js & NVM

This guide installs Node.js using NVM (Node Version Manager).

---

## Step 1. Install NVM

```bash
paru -S nvm
```

---

## Step 2. Configure NVM

### Bash

```bash
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.bashrc
echo '[ -s /usr/share/nvm/init-nvm.sh ] && source /usr/share/nvm/init-nvm.sh' >> ~/.bashrc
source ~/.bashrc
```

### Zsh

```bash
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.zshrc
echo '[ -s /usr/share/nvm/init-nvm.sh ] && source /usr/share/nvm/init-nvm.sh' >> ~/.zshrc
source ~/.zshrc
```

---

## Step 3. Install Node.js

Install the latest LTS version.

```bash
nvm install --lts
nvm use --lts
nvm alias default lts/*
```

---

## Step 4. Install pnpm

```bash
npm install -g pnpm
```

---

## Step 5. Verify Installation

```bash
nvm --version
node -v
npm -v
pnpm -v
```

---

# Useful Commands

## List installed versions

```bash
nvm ls
```

## List available versions

```bash
nvm ls-remote
```

## Install a specific version

```bash
nvm install 22
```

## Switch version

```bash
nvm use 22
```

## Set default version

```bash
nvm alias default 22
```

## Remove a version

```bash
nvm uninstall 20
```

---

# Updating Node.js

```bash
nvm install --lts
nvm use --lts
nvm alias default lts/*
```

---

# Troubleshooting

### `nvm: command not found`

Reload your shell.

```bash
source ~/.zshrc
```

or

```bash
source ~/.bashrc
```