# Maintainer: Limao Luo <luolimao+AUR@gmail.com>

pkgname=gnome-agenda
pkgver=0.3.1.6
pkgrel=4
pkgdesc="Display calendars on the GNOME desktop tray. Supports Google Calendar, Novell Groupwise, Evolution and iCalendar"
arch=(any)
url=http://code.google.com/p/$pkgname/
license=(GPL2)
depends=(gnome-icon-theme python2-configobj python2-dateutil python2-dbus python2-lxml
    python2-pysqlite python2-sexy python2-vobject)
optdepends=('python2-evolution: Evolution plugin'
    'python2-gdata: Google calendar plugin')
makedepends=(python2-distribute)
source=(http://$pkgname.googlecode.com/svn/tags/agenda-$pkgver.tar.gz)
sha256sums=('eef88dd75e079b376b14ce4b4f61bfb9c079f70feda66b77807130c1937d9b1e')
sha512sums=('1ec811a27354c28f3c68d33c340e119369b7f9dd65383c7201441a26f8e3e0753c1430eea2eb3b1fc447ef33d5dc9062e457976885cc56a9822d0eb659bc68e7')

prepare() {
    cd agenda-$pkgver/
    for i in $(find -name '*.py') agenda-gtk; do
        sed -ri 's:^#!/usr/bin/(env )?python$:&2:' "$i"
    done
}

build() {
    cd agenda-$pkgver/
    python2 setup.py build
}

package() {
    cd agenda-$pkgver/
    python2 setup.py install --root="$pkgdir" --optimize=1
}
