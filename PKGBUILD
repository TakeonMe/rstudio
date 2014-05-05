pkgname=rstudio-desktop-bin
pkgver=0.98.507
pkgrel=1
pkgdesc="A new integrated development environment (IDE) for R (binary version from RStudio official website)"
arch=('x86_64')
license=('GPL')
url="http://www.rstudio.org/"
depends=('r>=2.11.1' 'qtwebkit')
conflicts=('rstudio-desktop' 'rstudio-desktop-git')
provides=("rstudio-desktop=${pkgver}")
options=(!strip)
md5sums='9a75bd0651270257607bd7a11b867324'
source=("http://download1.rstudio.org/rstudio-${pkgver}-amd64.deb")
install="$pkgname".install

package() {
  msg "Converting debian package..."
  cd "$srcdir"
  tar zxpf data.tar.gz -C "$pkgdir"
  install -dm755 "$pkgdir/usr/bin"
  cd "$pkgdir/usr/lib/rstudio/bin"
  rm lib*.so.*
  cd "$pkgdir/usr/bin"
  ln -s -f ../lib/rstudio/bin/rstudio rstudio-bin
}
