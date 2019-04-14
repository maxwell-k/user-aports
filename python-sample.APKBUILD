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
source="https://files.pythonhosted.org/packages/source/LETTER/${_pyname}/${_pyname}-${pkgver}.tar.gz"

builddir="$srcdir/$_pyname-$pkgver"

build() {
	cd "$builddir"
	python3 setup.py build
}

check() {
	cd "$builddir"
	python3 setup.py test
}

package() {
	cd "$builddir"
	python3 setup.py install --prefix=/usr --root="$pkgdir"
}

sha15sums="" # these last two lines will be replaced by 'abuild checksum'
# vim: ft=sh.apkbuild
