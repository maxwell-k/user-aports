# Contributor: Keith Maxwell <keith.maxwell@gmail.com>
# Maintainer: Keith Maxwell <keith.maxwell@gmail.com>
pkgname=NAME
_pyname=PYPI_NAME
pkgver=VERSION
pkgrel=0
pkgdesc=""
url=""
arch="noarch" # TODO: change to all if C code present
license="MIT" # TODO: check this! valid values in /usr/share/spdx/license.lst
depends="python3" # TODO: detected automatically if C code present, so remove
makedepends="python3-dev" # TODO: not required if no C code, so remove
source="https://files.pythonhosted.org/packages/source/LETTER/${_pyname}/${_pyname}-${pkgver}.tar.gz"

builddir="$srcdir/$_pyname-$pkgver"

build() {
	python3 setup.py build
}

check() {
	python3 setup.py test
}

package() {
	python3 setup.py install --prefix=/usr --root="$pkgdir"
}

sha15sums="" # these last two lines will be replaced by 'abuild checksum'
# vim: ft=sh.apkbuild
