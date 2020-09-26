pkgname=qtile-widget-scriptexit-git
_pkgname=qtile-widget-scriptexit
pkgver=0.0.1
pkgrel=1
provides=("$_pkgname")
conflicts=("$_pkgname")
pkgdesc="Qtile QuickExit widget but can run a script before exiting."
url="https://github.com/elparaguayo/qtile-widget-scriptexit.git"
license=("MIT")
depends=("python" "qtile")
source=("git+https://github.com/elparaguayo/$_pkgname.git")
md5sums=("SKIP")

pkgver()
{
  cd "$_pkgname"
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package()
{
  cd "$_pkgname"
  python setup.py install --root="$pkgdir"
}
