# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=qqc2-desktop-style
pkgver=6.1.0
pkgrel=1
pkgdesc='A style for Qt Quick Controls 2 to make it follow your desktop theme'
arch=(x86_64)
url='https://community.kde.org/Frameworks'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(gcc-libs
         glibc
         kcolorscheme
         kconfig
         kiconthemes
         kirigami
         qt6-base
         qt6-declarative
         sonnet)
makedepends=(extra-cmake-modules)
groups=(kf6)
source=(https://download.kde.org/stable/frameworks/${pkgver%.*}/$pkgname-$pkgver.tar.xz{,.sig})
sha256sums=('e91d9abcf9169eca357e7dc8b7fc504a3b7e5eff324feaa6ffecc8091e1622d9'
            'SKIP')
validpgpkeys=(53E6B47B45CEA3E0D5B7457758D0EE648A48B3BB  # David Faure <faure@kde.org>
              E0A3EB202F8E57528E13E72FD7574483BB57B18D) # Jonathan Esk-Riddell <jr@jriddell.org>

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
