# 📦 Installation Guide - Package Installer CLI

Complete installation guide for **Package Installer CLI** across multiple package managers and platforms.

## 🚀 Quick Installation

### Node.js / npm

[![npm version](https://img.shields.io/npm/v/@0xshariq/package-installer.svg)](https://www.npmjs.com/package/@0xshariq/package-installer)

```bash
# Using npm (recommended)
npm install -g @0xshariq/package-installer

# Using yarn
yarn global add @0xshariq/package-installer

# Using pnpm
pnpm add -g @0xshariq/package-installer

# Run without installing (npx)
npx @0xshariq/package-installer create my-app
```

**Official Package**: [npmjs.com/package/@0xshariq/package-installer](https://www.npmjs.com/package/@0xshariq/package-installer)

---

## 🐍 Python Installation

[![PyPI version](https://img.shields.io/pypi/v/devforge.svg)](https://pypi.org/project/devforge/)

```bash
# Using pip
pip install devforge

# Using pip3
pip3 install devforge

# Install for current user only
pip install --user devforge

# Upgrade to latest version
pip install --upgrade devforge
```

**Official Package**: [pypi.org/project/devforge](https://pypi.org/project/devforge/)

**Source Code**: [github.com/0xshariq/py_package_installer_cli](https://github.com/0xshariq/py_package_installer_cli)

---

## 🦀 Rust Installation

[![Crates.io version](https://img.shields.io/crates/v/devforge.svg)](https://crates.io/crates/devforge)

```bash
# Using cargo
cargo install devforge

# Install from git (latest)
cargo install --git https://github.com/0xshariq/rust_package_installer_cli

# Update to latest version
cargo install devforge --force
```

**Official Package**: [crates.io/crates/devforge](https://crates.io/crates/devforge)

**Source Code**: [github.com/0xshariq/rust_package_installer_cli](https://github.com/0xshariq/rust_package_installer_cli)

---

## 💎 Ruby Installation

[![Gem Version](https://img.shields.io/gem/v/devforge.svg)](https://rubygems.org/gems/devforge)

```bash
# Using gem
gem install devforge

# Install for current user
gem install --user-install devforge

# Update to latest version
gem update devforge
```

**Official Package**: [rubygems.org/gems/devforge](https://rubygems.org/gems/devforge)

**Source Code**: [github.com/0xshariq/ruby_package_installer_cli](https://github.com/0xshariq/ruby_package_installer_cli)

---

## 🐹 Go Installation

```bash
# Using go install
go install github.com/0xshariq/go_package_installer_cli@latest

# Clone and build from source
git clone https://github.com/0xshariq/go_package_installer_cli.git
cd go_package_installer_cli
go build -o pi
sudo mv pi /usr/local/bin/
```

**Source Code**: [github.com/0xshariq/go_package_installer_cli](https://github.com/0xshariq/go_package_installer_cli)

---

## 🍺 Homebrew Installation

### Install via Homebrew Tap

```bash
# Add the tap
brew tap 0xshariq/devforge

# Install devforge
brew install devforge

# Install with alias 'pi'
brew install devforge --with-alias=pi

# Update to latest version
brew upgrade devforge
```

### Alternative Installation Methods

```bash
# Install directly from formula URL
brew install https://raw.githubusercontent.com/0xshariq/homebrew-devforge/main/Formula/devforge.rb

# Install with custom alias
brew install devforge && ln -sf $(brew --prefix)/bin/devforge /usr/local/bin/pi
```

---

## 🐳 Docker Installation

[![Docker Hub](https://img.shields.io/docker/v/0xshariq/devforge?label=Docker%20Hub)](https://hub.docker.com/r/0xshariq/devforge)

### Pull and Run

```bash
# Pull latest image
docker pull 0xshariq/devforge:latest

# Run interactively
docker run -it --rm \
  -v "$(pwd)":/home/pi/projects \
  -v ~/.gitconfig:/home/pi/.gitconfig:ro \
  -v ~/.ssh:/home/pi/.ssh:ro \
  0xshariq/devforge:latest

# Create new project
docker run -it --rm \
  -v "$(pwd)":/home/pi/projects \
  0xshariq/devforge:latest create my-app
```

### Docker Compose

```yaml
# docker-compose.yml
version: '3.8'
services:
  package-installer:
    image: 0xshariq/devforge:latest
    volumes:
      - .:/home/pi/projects
      - ~/.gitconfig:/home/pi/.gitconfig:ro
      - ~/.ssh:/home/pi/.ssh:ro
    stdin_open: true
    tty: true
```

```bash
# Run with docker-compose
docker-compose run --rm package-installer
```

**Docker Hub**: [hub.docker.com/r/0xshariq/devforge](https://hub.docker.com/r/0xshariq/devforge)

---

## Chocolatey Installation
Coming Soon...
---

## 📋 Installation Verification

After installation, verify the CLI is working correctly:

```bash
# Check version
pi --version

# Check installation
pi doctor

# Run help command
pi --help

# Create test project
pi create test-project
```

---

## 🔧 Manual Installation

### From Source (Node.js)

```bash
# Clone repository
git clone https://github.com/0xshariq/devforge.git
cd devforge

# Install dependencies
npm install

# Build the CLI
npm run build

# Link globally
npm link

# Verify installation
pi --version
```

### Binary Releases

Download pre-compiled binaries from GitHub Releases:

```bash
# Linux/macOS
curl -L https://github.com/0xshariq/devforge/releases/latest/download/pi-linux -o pi
chmod +x pi
sudo mv pi /usr/local/bin/

# Windows
# Download pi-windows.exe from GitHub Releases
```

---

## 🚫 Uninstallation

### Remove from Different Package Managers

```bash
# npm
npm uninstall -g @0xshariq/package-installer

# pip
pip uninstall devforge

# cargo
cargo uninstall devforge

# gem
gem uninstall devforge

# homebrew
brew uninstall devforge
brew untap 0xshariq/devforge

# docker
docker rmi 0xshariq/devforge
```

### Clean Up Cache and Config

```bash
# Remove cache directory
rm -rf ~/.devforge

# Remove npm cache (if installed via npm)
npm cache clean --force
```

---

## 🛠️ Troubleshooting

### Common Issues

#### Permission Errors (Linux/macOS)
```bash
# Fix npm permissions
sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}

# Use npx instead
npx @0xshariq/package-installer create my-app
```

#### Command Not Found
```bash
# Add to PATH (add to ~/.bashrc or ~/.zshrc)
export PATH="$PATH:$HOME/.local/bin"

# Reload shell
source ~/.bashrc
```

#### Package Manager Issues
```bash
# Clear package manager cache
npm cache clean --force
pip cache purge
cargo clean
gem cleanup
```

### Getting Help

- **Documentation**: [README.md](README.md)
- **GitHub Issues**: [github.com/0xshariq/devforge/issues](https://github.com/0xshariq/devforge/issues)
- **Discussions**: [github.com/0xshariq/devforge/discussions](https://github.com/0xshariq/devforge/discussions)

---

## 🔗 Official Links

| Package Manager | Official Package URL |
|-----------------|----------------------|
| **npm** | [npmjs.com/package/@0xshariq/package-installer](https://www.npmjs.com/package/@0xshariq/package-installer) |
| **PyPI** | [pypi.org/project/devforge](https://pypi.org/project/devforge/) |
| **Crates.io** | [crates.io/crates/devforge](https://crates.io/crates/devforge) |
| **RubyGems** | [rubygems.org/gems/devforge](https://rubygems.org/gems/devforge) |
| **Docker Hub** | [hub.docker.com/r/0xshariq/devforge](https://hub.docker.com/r/0xshariq/devforge) |

| Source Code | Repository URL |
|-------------|----------------|
| **Main (Node.js)** | [github.com/0xshariq/devforge](https://github.com/0xshariq/devforge) |
| **Python** | [github.com/0xshariq/py_package_installer_cli](https://github.com/0xshariq/py_package_installer_cli) |
| **Rust** | [github.com/0xshariq/rust_package_installer_cli](https://github.com/0xshariq/rust_package_installer_cli) |
| **Ruby** | [github.com/0xshariq/ruby_package_installer_cli](https://github.com/0xshariq/ruby_package_installer_cli) |
| **Go** | [github.com/0xshariq/go_package_installer_cli](https://github.com/0xshariq/go_package_installer_cli) |

---

**Choose your preferred installation method and start building amazing projects! 🚀**

For more information, see the [main documentation](README.md).