# Maintainer: lluixhi <lluixhi@gmail.com>

pkgname=gtorrent-ncurses
# TODO Read pkgver somehow from the repo.
pkgver=0.0.1
pkgrel=2
pkgdesc='A minimalist bittorrent client written by the 4chan technology board (NCurses Edition).'
arch=('i686' 'x86_64')
url="https://github.com/gtorrent/gtorrent-ncurses"
license=('GPLv3')
depends=('boost' 'libtorrent-rasterbar-1' 'ncurses-git-cxx')
makedepends=('cmake' 'git')
optdepends=()
provides=("${pkgname}")
conflicts=("${pkgname}")
source=("git://github.com/gtorrent/gtorrent-ncurses.git")
md5sums=('SKIP')

prepare() {
    # Initialize Core
    cd "$srcdir/gtorrent-ncurses"
    git submodule init
    git submodule update
}

build() {
    # Build the Package
    cd "$srcdir/gtorrent-ncurses"
    mkdir -p build/
    cd build/
    cmake .. -DPREFIX=/usr
    make -j`nproc`
}

package() {
    cd "$srcdir/gtorrent-ncurses/build"
    make DESTDIR="$pkgdir" install
}
