# Maintainer: Case Duckworth <cased123@gmail.com>

pkgname=dmenu-duck-git
_pkgname=dmenu
pkgver=41.a4f17f5
pkgrel=1
pkgdesc="Dynamic menu extended - fork of a fork."
arch=('i686' 'x86_64')
url=https://github.com/duckwork/dmenu
license=('MIT')
depends=('libxft' 'libxinerama')
makedepends=('git')
provides=('dmenu')
conflicts=('dmenu')
source=("$_pkgname::git+https://github.com/duckwork/dmenu.git#branch=master")
sha256sums=('SKIP')

pkgver() {
    cd "$srcdir/$_pkgname"
    echo $(git rev-list --count HEAD).$(git rev-parse --short HEAD)
}

build() {
    cd "$srcdir/$_pkgname"
    make
}

package() {
    cd "$srcdir/$_pkgname"
    make PREFIX=/usr DESTDIR="$pkgdir" install
    install -D -m644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
