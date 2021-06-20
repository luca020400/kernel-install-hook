# Maintainer: Tilmann Meyer <allescrafterx@gmail.com>

pkgname=kernel-install-hook
pkgver=0.1.2
pkgrel=1
pkgdesc="kernel-install add/remove hook"
url=https://systemd.io/BOOT_LOADER_SPECIFICATION
arch=('any')
license=('MIT')
depends=('systemd')
source=(
  "60-kernel-install-remove.hook"
  "90-kernel-install-add.hook"
  "override.hook"
  "kernel-install"
)
sha256sums=('3b065aa2c405b720ae8b32c224f2c3a49197b716657232899da3e94d2de688ae'
            '1353b581e2db787e31802881b73e01d28c24ca66487ddca114796cffbc41fe38'
            'ab2f65c7cbc05c59a8031c33f987db17a2f6345372216e5ee7cda64ddc6e8c3a'
            'd299d9b3440c0aa3c81e17a9f7f0ea3e0f0f3c9c6f5f8e4078789ebd893768eb')

package() {
  # Install alpm hooks
  install -Dm644 "${srcdir}/60-kernel-install-remove.hook" "${pkgdir}/usr/share/libalpm/hooks/60-kernel-install-remove.hook"
  install -Dm644 "${srcdir}/90-kernel-install-add.hook" "${pkgdir}/usr/share/libalpm/hooks/90-kernel-install-add.hook"
  # Override mkinitcpio alpm hooks
  install -Dm644 "${srcdir}/override.hook" "${pkgdir}/etc/pacman.d/hooks/60-mkinitcpio-remove.hook"
  install -Dm644 "${srcdir}/override.hook" "${pkgdir}/etc/pacman.d/hooks/90-mkinitcpio-install.hook"
  # Install alpm scripts
  install -Dm755 "${srcdir}/kernel-install" "${pkgdir}/usr/share/libalpm/scripts/kernel-install"
}
