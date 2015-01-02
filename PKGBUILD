# Maintainer: Sung Pae <self@sungpae.com>
pkgname=slock-nerv
pkgver=
pkgrel=1
pkgdesc="Custom slock build"
arch=('x86_64')
license=('MIT')
groups=('nerv')
depends=('libxext' 'powerctl')
makedepends=('git')
provides=('slock')
conflicts=('slock')
replaces=('slock-guns')

pkgver() {
    printf %s "$(git describe --long --tags | tr - .)"
}

build() {
    cd "$startdir"
    make -j $(grep -c ^processor /proc/cpuinfo)
}

package() {
    cd "$startdir"
    make PREFIX=/usr DESTDIR="$pkgdir/" install
}
