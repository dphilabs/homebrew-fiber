# Homebrew Tap for Fiber

Official Homebrew tap for **[Fiber](https://github.com/dphilabs/fiber)**

## Installation

Install `fiber` directly (this automatically registers the `dphilabs/fiber` tap, provisions an isolated Python 3.12 runtime under `libexec`, and installs `redis`):

```bash
brew install dphilabs/fiber/fiber
```

Or tap the repository explicitly first:

```bash
brew tap dphilabs/fiber
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
brew services start dphilabs/fiber/fiber
```

3. **Check service status and logs:**
```bash
brew services info dphilabs/fiber/fiber
tail -f $(brew --prefix)/var/log/fiber/daemon.log
```

## Upgrading & Uninstalling

```bash
# Upgrade to the latest release
brew update
brew upgrade dphilabs/fiber/fiber

# Stop service and uninstall
brew services stop dphilabs/fiber/fiber
brew uninstall dphilabs/fiber/fiber
```
