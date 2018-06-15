# Maintainer: Bruno Pagani <archange@archlinux.org>
# Contributor: cth451 <cth451@gmail.com>
# Modified for Namib by frederic2ec

pkgname=materia-namib-gtk-theme
pkgver=20180519
pkgrel=1
pkgdesc="A Material Design theme for GNOME/GTK+ based desktop environments with Numix color"
arch=('any')
url="https://github.com/nana-4/materia-theme"
license=('GPL')
makedepends=('sassc' 'parallel')
depends=('gtk3' 'gnome-themes-extra')
optdepends=('gtk-engine-murrine: for gtk2 theme')
source=(${pkgname}-${pkgver}.tar.gz::"https://github.com/nana-4/materia-theme/archive/v${pkgver}.tar.gz")
sha256sums=('4d9bec034767e2a08f843e1dd61bdf7ead97621c2977886a9288fb898342578f')

prepare() {
	cd materia-theme-${pkgver}
    	find ./ -type f -exec sed -i 's/01A299/d64937/g' {} \;
	find ./ -type f -exec sed -i 's/4285F4/d64937/g' {} \;
}

build() {
	cd materia-theme-${pkgver}
	./parse-sass.sh
	./render-assets.sh
}

package() {
    cd  materia-theme-${pkgver}
    install -d "${pkgdir}"/usr/share/themes
    ./install.sh -n "Materia-Namib" -d "${pkgdir}"/usr/share/themes
}


