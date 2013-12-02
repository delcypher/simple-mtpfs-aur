# Maintainer: Dan Liew <dan at su-root dot co dot uk>
pkgname=simple-mtpfs
pkgver=0.1
pkgrel=4
pkgdesc="A FUSE filesystem that supports reading/writing from MTP devices"
arch=('i686' 'x86_64')
url="https://github.com/phatina/simple-mtpfs/"
license=('GPL2')
depends=('libmtp' 'fuse' 'gcc-libs')
makedepends=('autoconf' 'automake' 'make' 'pkg-config')
options=(strip)
changelog=${pkgname}.changelog
source=(https://github.com/phatina/simple-mtpfs/archive/$pkgname-$pkgver.tar.gz)
md5sums=('36e3787ccca7f0304ae34f7344695c35')

build() {
  cd "$srcdir/$pkgname-$pkgname-$pkgver"
  if [[ ! -e "./configure" ]]; then 
    ./autogen.sh 
    ./configure --prefix=/usr
  else
    ./config.status
  fi
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
