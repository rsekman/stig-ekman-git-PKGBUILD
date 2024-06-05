# Maintainer: Robin Ekman < robin [dot] seth [dot] ekman [at] gmail [dot] com >
# Contributor: Kazuo Teramoto < kaz.rag [at] gmail [dot] com >

_pkgname=stig
pkgname=${_pkgname}-ekman-git
pkgver=v0.12.9a0.r74.geb0003a8
pkgrel=1
pkgdesc='TUI and CLI client for the Transmission daemon'
url='https://github.com/rndusr/stig'
provides=("stig=${pkgver}")
depends=(
    'python'
    'python-urwid>=2.6.12'
    'python-urwidtrees'
    'python-aiohttp'
    'python-pyxdg'
    'python-blinker'
    'python-natsort'
    'python-bidict'
)
makedepends=('python-setuptools')
optdepends=(
    'python-pprofile: profiling'
    'python-setproctitle: prettifies the process name'
)
conflicts=('stig' 'stig-git')
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
