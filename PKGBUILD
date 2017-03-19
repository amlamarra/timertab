# Maintainer: amlamarra <amlamarra AT archlinux DOT us>
pkgname=timertab
pkgver=1.0
pkgrel=1
pkgdesc="An easy way to manage your Systemd Timers."
arch=('any')
url="https://github.com/amlamarra/timertab"
depends=('bash' 'systemd')
#makedepends=('git')
source=("https://raw.githubusercontent.com/amlamarra/timertab/master/$pkgname")
sha256sums=('bb29fec17f016bbba92902f510b425bcb01e9e6ef55108a8959cef5692371c43')

package () {
	install -D -t "$pkgdir/usr/bin/$pkgname"
}
