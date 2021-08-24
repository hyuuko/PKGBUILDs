My Arch Linux PKGBUILDs.

## Install

```bash
cd <PKGBUILD_DIR>
# Temporarily exported to makepkg to set the build directory to an existing tmpfs
BUILDDIR=/tmp/makepkg
# Build the package and install needed dependencies
makepkg -s
# Install the package, same as `pacman -U pkgname-pkgver.pkg.tar.zst`
makepkg -i
```

## Upgrade

Modify the `pkgver` field in the PKGBUILD file, then:

```bash
cd <PKGBUILD_DIR>
# Generate new checksums
updpkgsums
# Generate .SRCINFO
makepkg --printsrcinfo > .SRCINFO
```
