#Maintainer: Andrzej Giniewicz <gginiu@gmail.com>
#Contributor: Firmicus <firmicus āt gmx dōt net>

pkgname=fonttools
pkgver=2.3
pkgrel=2
pkgdesc="Converts OpenType and TrueType fonts to and from XML"
url="http://sourceforge.net/projects/fonttools/"
license=("BSD")
arch=('i686' 'x86_64')
depends=("python2-numpy")
makedepends=("python2-distribute")
source=(http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz)
md5sums=('502cdf6662e1d075f1902fbd995eaace')

build() {
  cd "$srcdir"/$pkgname-$pkgver
  python2 setup.py install --root="$pkgdir" --optimize=1
  install -D -m755 LICENSE.txt "$pkgdir"/usr/share/licenses/fonttools/LICENSE
  chmod oga+r "$pkgdir"/usr/share/man/man1/ttx.1
  sed -i -e "s|#![ ]*/usr/bin/env python$|#!/usr/bin/env python2|" \
    $(find "${pkgdir}" -name '*.py')
}

