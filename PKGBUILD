# Maintainer: Pellegrino Prevete <pellegrinoprevete@gmail.com>
# Contributor: David Runge <dvzrv@archlinux.org>

_pkgname=mkinitcpio-archiso
pkgname=$_pkgname-encryption
pkgver=65
pkgrel=1
pkgdesc="Initcpio scripts used by archiso (encrypt hook support)"
arch=(any)
_gitlab="https://gitlab.archlinux.org"
url="${_gitlab}/mkinitcpio/mkinitcpio-archiso/-/merge_requests/25"
license=(GPL3)
depends=(bash device-mapper mkinitcpio cryptsetup)
conflicts=('mkinitcpio-archiso')
provides=('mkinitcpio-archiso')
makedepends=(git)
checkdepends=(shellcheck shfmt)
optdepends=(
  'curl: for PXE over HTTP'
  'mkinitcpio-nfs-utils: for PXE over NFS'
  'nbd: for PXE over NBD'
  'pv: for status display during copy to RAM'
)
_commit="49e0273313d325c8f7ca3bbf24678ab196fead66"
source=("${pkgname}::git+${_gitlab}/tallero/${_pkgname}.git#commit=${_commit}")
sha256sums=('SKIP')

check() {
  make -k check -C $pkgname
}

package() {
  make DESTDIR="$pkgdir/" PREFIX=/usr install -C $pkgname
}
