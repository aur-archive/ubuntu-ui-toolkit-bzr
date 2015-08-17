# Maintainer: Riccardo Ferrazzo <f.riccardo87@gmail.com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=ubuntu-ui-toolkit-bzr
pkgver=1171
pkgrel=1
pkgdesc="Ubuntu UI Toolkit Preview"
arch=('i686' 'x86_64')
url="https://launchpad.net/ubuntu-ui-toolkit"
license=('GPL')
depends=('qt5-graphicaleffects' 'libnih' 'qt5-pim-git' 'qt5-feedback-git')
makedepends=('bzr')
options=('!makeflags')
source=('bzr+lp:ubuntu-ui-toolkit'
        'python.patch'
        'qtpim.patch')
md5sums=('SKIP'
         'ec8c41857bd36870f48cdf34345cb484'
         '64fb831efc4770b05d01eaf9ceb35ff3')

prepare() {
  cd $srcdir
  patch -Np1 -i ../python.patch
  patch -Np1 -i ../qtpim.patch
}

pkgver() {
  cd ubuntu-ui-toolkit
  bzr revno
}

build() {
  cd ubuntu-ui-toolkit
  qmake-qt5
  make
}

package() {
  cd ubuntu-ui-toolkit
  make INSTALL_ROOT="${pkgdir}" install
}
