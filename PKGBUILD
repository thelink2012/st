# This is a small PKGBUILD for this little piece of fork.
# Based on the PKGBUILD from st-git (https://aur.archlinux.org/packages/st-git/)

_pkgname=st
pkgname=st-thelink2012
pkgver=0.7.45.g92d9ad0
pkgrel=1
pkgdesc='Simple virtual terminal emulator for X'
url='https://github.com/thelink2012/st'
arch=('i686' 'x86_64')
license=('MIT')
options=('zipman')
depends=('libxft')
makedepends=('ncurses' 'libxext' 'git')
epoch=1

provides=("${_pkgname}")
conflicts=("${_pkgname}", "st-git", "xst-git")

pkgver() {
	cd "${startdir}"
	git describe --tags | sed 's/-/./g'
}

prepare() {
	cd "${startdir}"
	sed '/@tic/d' -i Makefile
}

build() {
	cd "${startdir}"
	make
}

package() {
	cd "${startdir}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
	install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
	install -Dm644 README.md "${pkgdir}/usr/share/doc/${pkgname}/README"
}

