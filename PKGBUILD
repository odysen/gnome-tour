# Maintainer: ant <ant@national.shitposting.agency>
# Adapted-from: Rafael Fontenelle <rafaelff@gnome.org>

pkgname=gnome-tour
pkgver=43.0.0
pkgrel=1
pkgdesc="A guided tour and greeter for Odysen Desktop"
arch=(x86_64)
url="https://github.com/odysen/${pkgname}"
license=('GPL')
depends=('libadwaita')
makedepends=('rust' 'meson' 'git')
checkdepends=('appstream-glib')
provides=(${pkgname})
conflicts=(${pkgname}-git)
source=("git+$url")
md5sums=('SKIP')

build() {
  arch-meson ${pkgname} build
  meson compile -C build
}

check() {
  meson test -C build --print-errorlogs
}

package() {
  meson install -C build --destdir="$pkgdir"
}
