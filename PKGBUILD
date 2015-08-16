# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=kf5-qt5-svg-git
pkgver=v5.1.0.beta1.4.ged11da0
pkgrel=1
pkgdesc="A cross-platform application and UI framework (QtSvg)"
arch=('i686' 'x86_64')
url="http://qt-project.org/"
license=('GPL3' 'LGPL')
depends=('kf5-qt5-base-git')
makedepends=('git')
provides=('kf5-qt5-svg')
options=('!libtool')
source=(git://gitorious.org/qt/qtsvg.git)
md5sums=('SKIP')

pkgver() {
  cd qtsvg
  git describe --always | sed 's|-|.|g'
}

prepare() {
  cd qtsvg
  git checkout dev
}

build() {
  export QT_SELECT=kf5

  cd qtsvg
  qtchooser -run-tool=qmake
  make
}

package() {
  cd qtsvg
  make INSTALL_ROOT="${pkgdir}" install
}
