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
  "kernel-install"
)
sha256sums=('3b065aa2c405b720ae8b32c224f2c3a49197b716657232899da3e94d2de688ae'
            '1353b581e2db787e31802881b73e01d28c24ca66487ddca114796cffbc41fe38'
            '7693a0ebb543d6b04988d7e8e8e58e9bfd2a73e67b0a22143172f25cad53d6ef')

package() {
  install -Dm644 "${srcdir}/60-kernel-install-remove.hook" "${pkgdir}/usr/share/libalpm/hooks/60-kernel-install-remove.hook"
  install -Dm644 "${srcdir}/90-kernel-install-add.hook" "${pkgdir}/usr/share/libalpm/hooks/90-kernel-install-add.hook"
  install -Dm755 "${srcdir}/kernel-install" "${pkgdir}/usr/share/libalpm/scripts/kernel-install"
}
