# Maintainer: qs9rx < that nick at enjoys dÃ¶t it>
pkgname=qeu
pkgver=0.3
pkgrel=1
pkgdesc="Quake Editing Utilities"
arch=('x86_64' 'i686')
url="http://www.gamers.org/pub/idgames2/utils/bsp_pak_tools/qeu03.zip"
depends=('glibc')
license=('custom')
source=("http://www.gamers.org/pub/idgames2/utils/bsp_pak_tools/qeu03.zip"
  "compileon64bit.patch"
  "COPYING")
sha1sums=('3df3a6756fa4235d2674c5f209639169580fac91'
  'b916d697ea23820707d1ae267ecb4288b7ae9dd7'
  '240088f340fa33bd15cec1140701a5702a53c36b')

build() {
  cd "${srcdir}"
  patch -Np1 -i ../compileon64bit.patch
  make
}

package() {
  cd "${srcdir}"
  install -Dm644 COPYING "$pkgdir/usr/share/licenses/$pkgname/COPYING"
  install -d "$pkgdir/usr/bin"
  install -Dm755 {repak,rewad,rewad2,sprview,unbsp,unpak,unwad,unwad2} $pkgdir/usr/bin/
}
