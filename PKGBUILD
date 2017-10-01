# Maintainer: Cristian Porras <porrascristian@gmail.com>

pkgname=valentina
pkgver=0.5.0
pkgrel=2
pkgdesc="Cloth patternmaking software - Stable Release"
arch=('i686' 'x86_64')
url="http://valentina-project.org/"
license=('GPL3')
source=('https://bitbucket.org/dismine/valentina/get/v0.5.0.zip')
depends=('qt5-svg' 'poppler' 'qt5-xmlpatterns' )
makedepends=('qt5-tools' 'unzip' 'sed')

build() {
  cd "$srcdir/dismine-valentina-31c95eadca8b"
  find . -type f -print0 | xargs -0 sed -i /QForeachContainer/d
  qmake PREFIX=/usr PREFIX_LIB=/usr/lib Valentina.pro -r \
    	CONFIG+=noTests CONFIG+=no_ccache CONFIG+=noRunPath \
	CONFIG+=noDebugSymbols
  make
}

package() {
  cd "$srcdir/dismine-valentina-31c95eadca8b"
  INSTALL_ROOT="$pkgdir/" make install
}
 
sha512sums=('3e69f965de1f8179850a8c6a5a0d3b5e87384158191b9c4a3647a5421d1efe567e98298bd8f47a8288eac358520469ae7979a4a61df64ccfbeb1a36fb231efcf')
