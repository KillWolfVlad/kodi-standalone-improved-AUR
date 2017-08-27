# Maintainer (master-improved branch): KillWolfVlad <github.com/KillWolfVlad>
# Maintainer (master branch): graysky <graysky AT archlinux DOT us>

# Do NOT attempt to use this package on Arch ARM! This is only for x86_64/i686.
# You have been warned.

pkgname=kodi-standalone-improved
pkgver=1.93
pkgrel=2
pkgdesc="Systemd service to run kodi in stand-alone mode without a DE or WM"
arch=('x86_64')
url="https://github.com/KillWolfVlad/kodi-standalone-improved-AUR"
license=('GPL3')
depends=('systemd' 'xorg-server' 'xorg-xinit' 'kodi' 'polkit')
replaces=('xbmc-standalone-service')
conflicts=('kodi-standalone-service')
install=kodi.install
source=(
  "kodi.service"
  "kodi.sysusers"
  "kodi.tmpfiles"
)
sha256sums=('299c9a4676d3c15b495ad1b640609b797aeec1c8091e0a02e66f8f76711ebeef'
            'c6e4408833c572c1042e3562bd7440fa293438580c99bf0b7b0b17fbf208e942'
            'cdd87a1e8f859686c0fbf30f7af3135e909a08b40435d9b060b17b91621f529b')

package() {
  install -Dm 644 "${srcdir}/kodi.service" "${pkgdir}/usr/lib/systemd/system/kodi.service"
  install -Dm 644 "${srcdir}/kodi.sysusers" "${pkgdir}/usr/lib/sysusers.d/kodi.conf"
  install -Dm 644 "${srcdir}/kodi.tmpfiles" "${pkgdir}/usr/lib/tmpfiles.d/kodi.conf"
}
