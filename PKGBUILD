# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=qqc2-desktop-style
pkgver=6.2.0
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
makedepends=(extra-cmake-modules
             qt6-tools)
groups=(kf6)
source=(https://download.kde.org/stable/frameworks/${pkgver%.*}/$pkgname-$pkgver.tar.xz{,.sig})
sha256sums=('b8ed270d930aad05eadf1ec5a540870f1128d8c728d8616c40801d6980869b1c'
            'SKIP')
validpgpkeys=(53E6B47B45CEA3E0D5B7457758D0EE648A48B3BB # David Faure <faure@kde.org>
              E0A3EB202F8E57528E13E72FD7574483BB57B18D # Jonathan Esk-Riddell <jr@jriddell.org>
              90A968ACA84537CC27B99EAF2C8DF587A6D4AAC1 # Nicolas Fella <nicolas.fella@kde.org>
) 

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
