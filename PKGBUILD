# Maintainer: Chad "crossroads1112" Sharp <crossroads1112@riseup.net>
pkgname=pacupg
pkgver=r279.2c22abf
pkgrel=1
pkgdesc="Script that wraps package and AUR upgrades in btrfs snapshots and provides an easy way to roll them back"
arch=('any')
url="https://github.com/hcnelson99/pacupg-aur"
license=('GPL')
depends=('package-query' 'snapper' 'rsync')
optdepends=('pacaur: AUR support' 'grub-btrfs-git: Add btrfs snapshots to grub menu')
makedepends=()
source=(git+https://github.com/hcnelson99/pacupg.git)
md5sums=(SKIP)
install="${pkgname%-*}.install"

pkgver() {
  cd "pacupg"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
  cd "$srcdir/pacupg"
  install -Dm0755 pacupg      "$pkgdir/usr/bin/pacupg"
  install -Dm0644 pacupg.1    "$pkgdir/usr/share/man/man1/pacupg.1"
}
