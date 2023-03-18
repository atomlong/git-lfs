# Maintainer: Brendan Forster <brendan@github.com>

_realname="git-lfs"
pkgname=("${_realname}")
pkgver=3.3.0
pkgrel=1
pkgdesc="An open source Git extension for versioning large files"
install=git-lfs.install
arch=('any')
url="https://github.com/git-lfs/git-lfs"
src_zip_url="${url}/archive/v${pkgver}.zip"
license=('MIT')
groups=('VCS')

case "$CARCH" in
i686)
  zipname="git-lfs-windows-386-v$pkgver.zip"
  folder=git-lfs-$pkgver/
  sha256sum=81fd4b01719e1e0ccf347596293f19a07fba8573c6aee1e1521b2932d9b6179d
  exesuffix=
  ;;
x86_64)
  zipname="git-lfs-windows-amd64-v$pkgver.zip"
  folder=git-lfs-$pkgver/
  sha256sum=1df5874f22c35c679159f0aaf9e24333051f52768eade0204d22200b79141743
  exesuffix=
  ;;
aarch64)
  zipname="git-lfs-windows-arm64-v$pkgver.zip"
  folder=git-lfs-$pkgver/
  sha256sum=cf16b91ba10009b98bd641897609d9fd6994941705435aac60d12938322fbdbe
  exesuffix=
  ;;
esac

source=("https://github.com/github/git-lfs/releases/download/v$pkgver/$zipname"
	"$src_zip_url")

# Git LFS' source .zip now contains symbolic links that bsdtar does not like...
noextract=("${src_zip_url##*/}")

sha256sums=("$sha256sum" SKIP)
options=('!strip')

package() {
  install -d -m755 $pkgdir/$MSYSTEM_PREFIX/bin
  install -m755 $srcdir/$folder/git-lfs$exesuffix.exe $pkgdir/$MSYSTEM_PREFIX/bin/git-lfs.exe
  install -d -m755 $pkgdir/$MSYSTEM_PREFIX/share/doc/git-lfs
  install -m755 $srcdir/$folder/README.md $pkgdir/$MSYSTEM_PREFIX/share/doc/git-lfs/README.md
}
