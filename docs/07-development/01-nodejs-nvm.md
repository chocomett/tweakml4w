# 🟢 01. Node.js & NVM

This guide installs Node.js using NVM (Node Version Manager).

**⏱️ Estimated Time:** 5–10 minutes

---

## Step 1. Install NVM

Install NVM from the AUR.

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

Install pnpm globally.

```bash
npm install -g pnpm
```

---

## Verify

Verify that Node.js, npm, pnpm, and NVM were installed successfully.

```bash
nvm --version
node -v
npm -v
pnpm -v
```

---

## Notes

> 💡 Using **NVM** allows multiple Node.js versions to coexist and makes switching between projects much easier.

> 💡 I always install the latest **LTS** release and set it as the default version.

---

## Useful Commands

List installed versions.

```bash
nvm ls
```

List available versions.

```bash
nvm ls-remote
```

Install a specific version.

```bash
nvm install 22
```

Switch to a different version.

```bash
nvm use 22
```

Set the default version.

```bash
nvm alias default 22
```

Remove a version.

```bash
nvm uninstall 20
```

Update to the latest LTS version.

```bash
nvm install --lts
nvm use --lts
nvm alias default lts/*
```

---

## Troubleshooting

### ❌ `nvm: command not found`

Reload your shell.

```bash
source ~/.zshrc
```

or

```bash
source ~/.bashrc
```

Verify that NVM was loaded correctly.

```bash
command -v nvm
```

---

## Next

➡️ **02-postgresql.md**