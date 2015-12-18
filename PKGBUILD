
pkgname=kicad
pkgver=4.0.1
_pkgver=4.0
pkgrel=1
pkgdesc="Cross Platform and Open Source Electronics Design Automation Suite"
arch=('x86_64')
url="http://kicad-pcb.org/"
license=('GPL')
depends=('wxgtk2.9' 'hicolor-icon-theme' 'desktop-file-utils' 'libsm' 'boost-libs' 'glew' 'python2')
makedepends=('cmake' 'zlib' 'mesa' 'boost' 'gettext')
source=("https://launchpad.net/kicad/${_pkgver}/${pkgver}/+download/kicad-${pkgver}.tar.xz")
md5sums=('e85e9ab6ba7736377a31cfecc8aca4a6')

build() {
  mkdir -p build
  cd build

  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DKICAD_REPO_NAME=stable \
    -DKICAD_BUILD_VERSION=${pkgver} \
    -DKICAD_SKIP_BOOST=ON \
    -DBUILD_GITHUB_PLUGIN=ON
  make
}

package() {
  cd build

  make DESTDIR=${pkgdir} install
}