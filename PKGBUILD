
pkgname=conky-manager
pkgver=2.4
pkgbase=~136~ubuntu15.04.1
pkgrel=1
pkgdesc="GUI for managing Conky config files with options to browse and edit themes"
url="https://launchpad.net/conky-manager"
arch=('x86_64')
license=('GPL3')
depends=('cairo' 'conky' 'desktop-file-utils' 'gtk3' 'imagemagick' 'json-glib' 'libgee' 'libsoup' 'p7zip' 'rsync')
makedepends=('vala')
options=(!emptydirs)
install=conky-manager.install
source=(http://ppa.launchpad.net/teejee2008/ppa/ubuntu/pool/main/c/${pkgname}/${pkgname}_${pkgver}${pkgbase}.tar.xz)
sha512sums=('647fc3cc28ab4ad11303fcc35ff66962ec4c18813a38ce47269e32dbe864482f7da1ceeea1663bb4257c6bc210bd8c9c285603057a20f5cf8a007a3ee412d165')

build() {
  cd ${pkgname}-${pkgver}${pkgbase}
  make
}

package() {
  cd ${pkgname}-${pkgver}${pkgbase}
  make DESTDIR="${pkgdir}" install

  # fix make install problems
  rm "${pkgdir}/usr/bin/conky-manager-uninstall"
  find "${pkgdir}/usr/share/${pkgname}" -type f -print0 | xargs -0 chmod 644
  chmod 644 "${pkgdir}/usr/share/applications/conky-manager.desktop" \
    "${pkgdir}/usr/share/pixmaps/conky-manager.png"
}

# vim: ts=2 sw=2 et:
