pkgname=wii-libimgui
pkgver=1.91.9
pkgrel=1
pkgdesc="A lightweight GUI library"
arch=('x86_64')
url="https://github.com/dakotath/libImGui"
license=('MIT')
depends=('wii-sdl2' 'wii-sdl2_ttf' 'wii-sdl2_image' 'ppc-freetype' 'ppc-libpng' 'ppc-bzip2')
makedepends=('wii-cmake' 'make' 'devkitPPC')
source=("git+https://github.com/dakotath/libImGui.git")
sha256sums=('SKIP')  # Use 'SKIP' for git sources

build() {
    cd "$srcdir/libImGui"
    mkdir -p build

    # Override CFLAGS and CXXFLAGS to prevent invalid x86 flags
    export CFLAGS=""
    export CXXFLAGS=""
    export LDFLAGS=""

    /opt/devkitpro/portlibs/wii/bin/powerpc-eabi-cmake -S . -B build -DCMAKE_C_COMPILER_WORKS=1 -DCMAKE_CXX_COMPILER_WORKS=1
}

package() {
    cd "$srcdir/libImGui/build"
    make DESTDIR="$pkgdir" install -j$(nproc)
}
