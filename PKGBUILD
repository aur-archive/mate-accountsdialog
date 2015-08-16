# Maintainer : Martin Wimpress <code@flexion.org>

pkgname=mate-accountsdialog
pkgver=1.6.0
pkgrel=1
pkgdesc="An application to view and modify user accounts information for MATE."
url="https://github.com/NiceandGently/mate-accountsdialog"
arch=('i686' 'x86_64')
license=('GPL')
depends=('accountsservice' 'apg' 'dbus-glib' 'gtk2' 'iso-codes' 'mate-desktop'
         'mate-polkit' 'libunique')
makedepends=('mate-common' 'mate-doc-utils' 'perl-xml-parser')
options=('!emptydirs')
source=("https://github.com/NiceandGently/${pkgname}/archive/v${pkgver}.tar.gz")
sha1sums=('33704adbed045b60cbcd3e15ae83e3283765ef52')
install=${pkgname}.install

prepare() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    NOCONFIGURE=1 ./autogen.sh
}

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    ./configure \
        --prefix=/usr \
        --enable-systemd
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
