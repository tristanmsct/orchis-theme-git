# Maintainer: Mark Wagie <mark dot wagie at proton dot me>
pkgname=(
  'orchis-theme-git'
)
pkgbase=orchis-theme-git
pkgver=r699.g174e929
pkgrel=1
pkgdesc="A Material Design theme for GNOME/GTK based desktop environments."
arch=('any')
url="https://github.com/tristanmsct/Orchis-theme"
license=('GPL-3.0-or-later')
makedepends=(
  'git'
  'sassc'
)
optdepends=(
  'gnome-themes-extra: GTK2 theme support'
  'gtk-engine-murrine: GTK2 theme support'
  'kvantum-theme-orchis: Matching Kvantum theme'
  'tela-circle-icon-theme: Recommended icon theme'
  'vimix-cursors: recommended cursor theme'
)
options=('!strip')
install="${pkgbase%-git}.install"
source=('git+https://github.com/tristanmsct/Orchis-theme.git#branch=fix-gnome50-sidebar')
sha256sums=('SKIP')

pkgver() {
  cd Orchis-theme
  printf "r%s.g%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short=7 HEAD)"
}

package_orchis-theme-git() {
  provides=("${pkgname%-git}")
  conflicts=("${pkgname%-git}")

  cd Orchis-theme
  install -d "$pkgdir/usr/share/themes"
  ./install.sh -t all -c light dark -s compact -i arch -d "$pkgdir/usr/share/themes"
  mv "$pkgdir/usr/share/themes/Orchis-Dark-Compact" "$pkgdir/usr/share/themes/Orchis-Blue-Dark-Compact"
  mv "$pkgdir/usr/share/themes/Orchis-Light-Compact" "$pkgdir/usr/share/themes/Orchis-Blue-Light-Compact"
  rm -rf "$pkgdir"/usr/share/themes/*-hdpi
  rm -rf "$pkgdir"/usr/share/themes/*-xhdpi
}
