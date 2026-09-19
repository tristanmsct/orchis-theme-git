# Maintainer: Mark Wagie <mark dot wagie at proton dot me>
pkgname='orchis-theme-git'
pkgbase=orchis-theme-git
pkgver=2026.07.07.r5.ga4c48a4
pkgrel=1
pkgdesc="A Material Design theme for GNOME/GTK based desktop environments."
arch=('any')
url="https://github.com/vinceliuice/Orchis-theme"
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
source=('git+https://github.com/vinceliuice/Orchis-theme.git')
sha256sums=('SKIP')

pkgver() {
  cd Orchis-theme
  git describe --long --tags --abbrev=7 | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

package_orchis-theme-git() {
  provides=("${pkgname%-git}")
  conflicts=("${pkgname%-git}")

  cd Orchis-theme
  ./install.sh -t all -c light dark -s compact -i arch -d "$pkgdir/usr/share/themes"
  mv "$pkgdir/usr/share/themes/Orchis-Dark-Compact" "$pkgdir/usr/share/themes/Orchis-Blue-Dark-Compact"
  mv "$pkgdir/usr/share/themes/Orchis-Light-Compact" "$pkgdir/usr/share/themes/Orchis-Blue-Light-Compact"
  rm -rf "$pkgdir"/usr/share/themes/*-hdpi
  rm -rf "$pkgdir"/usr/share/themes/*-xhdpi
}
