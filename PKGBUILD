
pkgname=conky-manager
pkgver=1.2.0.1
pkgrel=1
pkgdesc="Simple tool for managing conky scripts. (stable version)"
arch=('x86_64')
url=http://teejeetech.blogspot.in/
license=('GPL2')
depends=(conky desktop-file-utils gtk3 libgee06 p7zip)
makedepends=(vala)
conflicts=(conky-manager-bzr)
options=(!emptydirs)
install=$pkgname.install
source=("http://ppa.launchpad.net/teejee2008/ppa/ubuntu/pool/main/c/${pkgname}/${pkgname}_${pkgver}.tar.gz")
sha256sums=('93c067221f053cf4296bf7a23be85d1148d54f37ade26225adcbc891c341b282')

build() {
  cd "$srcdir/$pkgname-$pkgver"

  make
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  make DESTDIR="$pkgdir" install
}
