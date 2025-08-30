# Maintainer: alec <alecvbnm@outlook.com>
pkgname=stow2gistow-git
pkgver=r2.aba9430
pkgrel=2
pkgdesc="Convert stow package to gistow package"
arch=(any)
url="https://github.com/Cricarvbnm/stow2gistow"
license=(MIT)
provides=(stow2gistow)
depends=(sed findutils rsync coreutils sh)
source=("git+${url}")
sha256sums=(SKIP)

package() {
  install -Dm755 ${srcdir}/${pkgname%-git}/stow2gistow -t ${pkgdir}/usr/bin/
}

pkgver() {
  cd "${srcdir}/${pkgname%-git}"
  ver=$(git describe --long --tags --abbrev=7 2>/dev/null | sed 's/^v//;s/-/+/g')
  if [ -z "$ver" ]; then
    printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
  fi
}

