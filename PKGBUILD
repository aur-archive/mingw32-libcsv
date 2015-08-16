# Maintainer: Marcel Schneider <marcel@coopmasters.de>
pkgname=mingw32-libcsv
_DOWNLOADNAME=libcsv
pkgver=3.0.3
pkgrel=1
pkgdesc="A library written in pure ANSI C89 that can read and write CSV data (mingw32)"
arch=('any')
url="http://libcsv.sourceforge.net/"
license=('LGPL')
depends=('mingw32-runtime')
makedepends=('mingw32-gcc')
options=('!strip' '!buildflags' '!libtool')
install=
source=(http://downloads.sourceforge.net/project/libcsv/libcsv/libcsv-${pkgver}/$_DOWNLOADNAME-${pkgver}.tar.gz)
md5sums=('d3307a7bd41d417da798cd80c80aa42a')

build() {
  mkdir -p $pkgdir/usr/i486-mingw32/{lib,include}
  cd $srcdir/$_DOWNLOADNAME-$pkgver
  unset LDFLAGS
  unset CXXFLAGS
  unset CFLAGS
  export CXX=i486-mingw32-g++
  export CC=i486-mingw32-gcc
  ./configure 	--prefix=/usr/i486-mingw32 \
		--host=i486-mingw32 \
		--build=i686-linux 
  make || return 1
  make DESTDIR=$pkgdir install
  #comment following line out, if you want man pages getting installed
  rm -rf $pkgdir/usr/i486-mingw32/share
}
