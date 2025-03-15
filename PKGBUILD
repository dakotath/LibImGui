pkgname=wii-libimgui
pkgver=1.91.9
pkgrel=1
pkgdesc="A lightweight GUI library"
arch=('x86_64')
url="https://github.com/your-repo/libImGui"
license=('MIT')
depends=('wii-sdl2' 'wii-sdl2_ttf' 'wii-sdl2_image' 'ppc-freetype' 'ppc-libpng' 'ppc-bzip2')
makedepends=('wii-cmake' 'make' 'gcc')
source=("git+https://github.com/dakotath/libImGui.git")
sha256sums=('SKIP')  # Use 'SKIP' for git sources

build() {
    cd "$srcdir/libImGui"
    mkdir -p build
    cd build
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr
    make
}

package() {
    cd "$srcdir/libImGui/build"
    make DESTDIR="$pkgdir" install
}
