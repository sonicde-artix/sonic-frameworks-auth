# Maintainer: artist for Artix Linux

pkgname=sonic-frameworks-auth
pkgver=6.26.0
pkgrel=1
pkgdesc='Abstraction to system policy and authentication features'
arch=(x86_64)
url="https://github.com/Sonic-DE/$pkgname"
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(libstdc++
         glibc
         sonic-frameworks-core-addons
         sonic-frameworks-windowsystem
         polkit-qt6
         qt6-base)
makedepends=(doxygen
             extra-cmake-modules
             qt6-tools)
groups=(sonicde-frameworks)
conflicts=(kauth)
provides=(kauth)
replaces=(kauth)
source=("$pkgname-$pkgver.tar.gz::${url}/archive/refs/tags/$pkgver.tar.gz")

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DCMAKE_INSTALL_LIBEXECDIR=lib \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
sha256sums=('3db9cd8091f7855a4b65332fdbb7adf7c6cfe17416ecf91443db2720fb94bd1a')
