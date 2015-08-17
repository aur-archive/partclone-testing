# Maintainer: jsteel <mail at jsteel dot org>
# Contributor: Ivan Sichmann Freitas <ivansichfreitas at gmail dot com>
# Contributor: Todd Partridge (Gen2ly) <toddrpartridge (at) gmail>
# Contributor: Franz Burgmann <f dot burgmann at gmail dot com>

pkgname=partclone-testing
_pkgname=partclone
pkgver=0.2.50
pkgrel=1
pkgdesc="Back up and restore used-blocks of a partition"
arch=('i686' 'x86_64')
url="http://partclone.org"
license=('GPL')
depends=('e2fsprogs' 'progsreiserfs' 'dosfstools' 'ncurses' 'ntfs-3g')
conflicts=('partclone' 'partclone-git')
provides=('partclone')
source=(http://sourceforge.net/projects/$_pkgname/files/testing/${_pkgname}_$pkgver.tar.gz)
md5sums=('40c66d1da81ce3dc4ebf9d11338b1af0')

build() {
  cd "$srcdir"/$_pkgname-$pkgver

  ./configure --prefix=/usr --enable-extfs --enable-reiserfs --enable-fat \
    --enable-hfsp --enable-btrfs --enable-ncursesw --enable-ntfs

  make
}

package() {
  cd "$srcdir"/$_pkgname-$pkgver

  make DESTDIR="$pkgdir" install
}
