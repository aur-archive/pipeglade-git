# Maintainer: Tim Cooper <tim.cooper@layeh.com>

pkgname=pipeglade-git
_pkgname=pipeglade
pkgver=r10.f58e4b3
pkgrel=1
pkgdesc="a helper program that displays graphical user interfaces for other programs"
arch=("x86_64" "i686")
url="http://pipeglade.boundp.org/"
license=("MIT")
depends=("gtk3" "glib2")
makedepends=()
source=("git+https://github.com/trebb/pipeglade")
md5sums=("SKIP")

pkgver() {
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd "$_pkgname"
  make
}

package() {
  cd "$_pkgname"
  install -D pipeglade "$pkgdir/usr/bin/pipeglade"
  install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/license"
  install -Dm644 pipeglade.1 "$pkgdir/usr/share/man/man1/pipeglade.1"
}
