# Contributor: Keith Maxwell <keith.maxwell@gmail.com>
# Maintainer: Keith Maxwell <keith.maxwell@gmail.com>
pkgname=NAME
_pyname=PYPI_NAME
pkgver=VERSION
pkgrel=0
pkgdesc=""
url=""
arch="noarch"
license="MIT"
depends="python3" # detected automatically if C code present
makedepends="python3-dev" # not required if no C code
source="http://downloads.sourceforge.net/$pkgname/$pkgname-$pkgver.tar.gz"

builddir="$srcdir/$_pyname-$pkgver"

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

sha15sums="" # these last two lines will be replaced by 'abuild checksum'
# vim: ft=sh.apkbuild
