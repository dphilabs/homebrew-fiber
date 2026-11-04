# Homebrew Tap for Fiber

Official Homebrew tap for **[Fiber](https://github.com/dphi-network/fiber)**

## Installation

Install `fiber` directly (this automatically registers the `dphi-network/fiber` tap, provisions an isolated Python 3.12 runtime under `libexec`, and installs `redis`):

```bash
brew install dphi-network/fiber/fiber
```

Or tap the repository explicitly first:

```bash
brew tap dphi-network/fiber
brew install fiber
```

## Quick Start & Background Service

1. **Bootstrap local workspace (`~/.anchor`) and node identity (`Ed25519` keys):**
```bash
fiber init
```

2. **Start Redis and the persistent Fiber Gateway daemon (`127.0.0.1:8356`):**
```bash
brew services start redis
brew services start dphi-network/fiber/fiber
```

3. **Check service status and logs:**
```bash
brew services info dphi-network/fiber/fiber
tail -f $(brew --prefix)/var/log/fiber/daemon.log
```

## Upgrading & Uninstalling

```bash
# Upgrade to the latest release
brew update
brew upgrade dphi-network/fiber/fiber

# Stop service and uninstall
brew services stop dphi-network/fiber/fiber
brew uninstall dphi-network/fiber/fiber
```
