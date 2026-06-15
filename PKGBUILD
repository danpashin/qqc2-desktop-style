# Maintainer: Antonio Rojas <arojas@archlinux.org>

pkgname=qqc2-desktop-style
pkgver=6.27.0
pkgrel=1
pkgdesc='A style for Qt Quick Controls 2 to make it follow your desktop theme'
arch=(x86_64)
url='https://develop.kde.org/products/frameworks/'
license=(LGPL-2.0-only
         LGPL-3.0-only)
depends=(libstdc++
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
source=(https://download.kde.org/stable/frameworks/${pkgver%.*}/$pkgname-$pkgver.tar.xz{,.sig}
        force-native-font-rendering.patch)
sha256sums=('6c005f06c5f8c4ac349238abf14999bb917215a8f7b8c51364e2fdd12e9e6355'
            'SKIP'
            '1e190bb84886c01329fdc6e5ebd10ba373a6e7d46cdf81d2810494d2fd91338c')
validpgpkeys=(53E6B47B45CEA3E0D5B7457758D0EE648A48B3BB  # David Faure <faure@kde.org>
              90A968ACA84537CC27B99EAF2C8DF587A6D4AAC1) # Nicolas Fella <nicolas.fella@kde.org>
prepare() {
  patch -d $pkgname-$pkgver -p1 < force-native-font-rendering.patch
}

build() {
  cmake -B build -S $pkgname-$pkgver \
    -DBUILD_TESTING=OFF
  cmake --build build
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}
