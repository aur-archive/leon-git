# Maintainer: Maxim Andersson <thesilentboatman@gmail.com>

pkgname=leon-git
_gitname=browser
pkgver=r22.a74aa27
pkgrel=1
pkgdesc="The soon-to-be default Evolve OS browser"
arch=('i686' 'x86_64')
url="https://github.com/zesterer/browser"
license=('unknown')
depends=('webkit2gtk' 'libgee06')
makedepends=('vala' 'git')
provides=('leon')
conflicts=('leon')
install=${pkgname}.install
source=('git://github.com/zesterer/browser.git')
sha256sums=('SKIP')

pkgver() {
  cd "${srcdir}/${_gitname}"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  cd "${srcdir}/${_gitname}"

  # Remove debug parameter 
  sed -i 's/ -g//g' cmd_to_compile.sh
}

build() {
  cd "${srcdir}/${_gitname}"

  ./cmd_to_compile.sh
}

package() {
  cd "${srcdir}/${_gitname}"

  install -D -m755 leon "${pkgdir}/usr/bin/leon"
}

# vim:set ts=2 sw=2 et:
