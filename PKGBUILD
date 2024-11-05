# Maintainer: lufia <lufia@lufia.org>

pkgname=plan9port-systemd-units
pkgver=0.1.0
pkgrel=1
pkgdesc='Systemd units for Plan 9 services'
arch=(any)
url=https://github.com/lufia/plan9port-systemd-units
license=(custom)
depends=(plan9port)

package() {
  install -Dm644 ../system/secstored.service "$pkgdir/usr/lib/systemd/system/secstored.service"
  install -Dm644 ../user/fontsrv.service "$pkgdir/usr/lib/systemd/user/fontsrv.service"
  install -Dm644 ../user/plumber.service "$pkgdir/usr/lib/systemd/user/plumber.service"
  install -Dm644 ../user/factotum.service "$pkgdir/usr/lib/systemd/user/factotum.service"
  install -Dm644 ../LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
