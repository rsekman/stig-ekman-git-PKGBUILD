# Maintainer: Robin Ekman < robin [dot] seth [dot] ekman [at] gmail [dot] com >
# Contributor: Kazuo Teramoto < kaz.rag [at] gmail [dot] com >

_pkgname=stig
pkgname=${_pkgname}-ekman-git
pkgver=v0.12.1a0.r92.gf0206012
pkgrel=1
pkgdesc='TUI and CLI client for the Transmission daemon'
url='https://github.com/rndusr/stig'
depends=(
    'python'
    'python-urwid'
    'python-urwidtrees'
    'python-aiohttp'
    'python-pyxdg'
    'python-blinker'
    'python-natsort'
)
makedepends=(
    'python-setuptools'
)
optdepends=(
    'python-pprofile: profiling'
    'python-setproctitle: prettifies the process name'
)
conflicts=(
    'stig'
    'stig-git'
)
license=('GPL')
arch=('any')

source=("git+https://github.com/rsekman/stig.git#branch=ekman")

sha256sums=('SKIP')


pkgver() {
  cd "$srcdir/${_pkgname}"
  git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd ${_pkgname}
	python setup.py build
}

package() {
	cd ${_pkgname}
	python setup.py install --root="${pkgdir}" --optimize=1 --skip-build
}
