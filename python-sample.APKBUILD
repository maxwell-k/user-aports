# Contributor: Keith Maxwell <keith.maxwell@gmail.com>
# Maintainer: Keith Maxwell <keith.maxwell@gmail.com>
pkgname=NAME
_pkgname=REAL_NAME
pkgver=VERSION
pkgrel=0
pkgdesc=""
url=""
arch="noarch"
license="MIT"
depends="python3"
makedepends="python3-dev"
source="http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz"

builddir="$srcdir/$_pkgname-$pkgver"

build() {
	cd "$builddir"
	python3 setup.py build
}

package() {
	cd "$builddir"
	python3 setup.py install --prefix=/usr --root="$pkgdir"
}

check() {
	cd "$builddir"
	python3 setup.py test
}

sha15sums="" # remove these last two lines and generate with 'abuild checksum'
# vim: ft=sh.apkbuild
