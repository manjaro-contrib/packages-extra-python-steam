# Maintainer: Mark Wagie <mark at manjaro dot org>

pkgname=python-steam
_name=${pkgname#python-}
pkgver=1.4.4
pkgrel=4
pkgdesc="Python package for interacting with Steam"
arch=('any')
url="https://github.com/ValvePython/steam"
license=('MIT')
depends=(
  'python'
  'python-cachetools'
  'python-pycryptodomex'
  'python-requests'
  'python-six'
  'python-vdf'
)
makedepends=(
  'python-build'
  'python-installer'
  'python-setuptools'
  'python-wheel'
)
source=("$_name-$pkgver.tar.gz::$url/archive/refs/tags/v$pkgver.tar.gz")
sha256sums=('2b5bd6911c0d4a7312f441b8d162b9d8d47c8bebb8efc6c8867393b0323fa52e')

build() {
  cd "$_name-$pkgver"
  python -m build --wheel --no-isolation
}

package() {
  cd "$_name-$pkgver"
  python -m installer --destdir="$pkgdir" dist/*.whl

  install -Dm644 LICENSE -t "$pkgdir/usr/share/licenses/$pkgname/"
}
