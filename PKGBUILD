
pkgname=kicad
pkgver=4.9.70
_commit=3ffa37c8b93a32c7864ac18eb13b63d869ee32b6
pkgrel=1
pkgdesc="Cross Platform and Open Source Electronics Design Automation Suite"
arch=('x86_64')
url="http://kicad-pcb.org/"
license=('GPL')
depends=('wxgtk2.9' 'hicolor-icon-theme' 'desktop-file-utils' 'libsm' 'boost-libs' 'glew' 'python2')
makedepends=('cmake' 'zlib' 'mesa' 'boost' 'gettext' 'swig')
source=("https://github.com/KiCad/kicad-source-mirror/archive/${_commit}.zip")
md5sums=('1978ca1af0d48fe919d1926cb3e95f39')

build() {
  mkdir -p build
  cd build

  cmake ../${pkgname}-source-mirror-${_commit} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DKICAD_SCRIPTING=ON \
    -DKICAD_SCRIPTING_MODULES=ON \
    -DBUILD_GITHUB_PLUGIN=ON 
  make
}

package() {
  cd build

  make DESTDIR=${pkgdir} install
}
