# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=qqc2-desktop-style
pkgver=5.248.0
pkgrel=2
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
source=(https://download.kde.org/unstable/frameworks/$pkgver/$pkgname-$pkgver.tar.xz{,.sig}
        https://invent.kde.org/frameworks/qqc2-desktop-style/-/commit/73303bf4.patch)
sha256sums=('7561607923c3290ee5ef0f131e513157d02cbf0a7fcc5aa308b652f234423dde'
            'SKIP'
            '018da87ce024c61316f118aca4b675c36a42a9be4cc82ff69e45a11435ca414a')
validpgpkeys=(53E6B47B45CEA3E0D5B7457758D0EE648A48B3BB  # David Faure <faure@kde.org>
              E0A3EB202F8E57528E13E72FD7574483BB57B18D) # Jonathan Esk-Riddell <jr@jriddell.org>

prepare() {
  patch -d $pkgname-$pkgver -p1 < 73303bf4.patch # Fix comboboxes with Qt 6.7
}

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
