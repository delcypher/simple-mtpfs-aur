# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Dan Liew <dan at su-root dot co dot uk>
pkgname=simple-mtpfs
pkgver=0.1
pkgrel=1
pkgdesc="A FUSE filesystem that supports reading/writing from MTP devices"
arch=('i686' 'x86_64')
url="https://github.com/phatina/simple-mtpfs/"
license=('GPL2')
groups=()
depends=('libmtp' 'fuse' 'gcc-libs' )
makedepends=('git' 'autoconf' 'make')
options=()
source=(https://github.com/phatina/simple-mtpfs/archive/$pkgname-$pkgver.tar.gz)
md5sums=('36e3787ccca7f0304ae34f7344695c35')

build() {
  cd "$srcdir/$pkgname-$pkgname-$pkgver"
  [[ ! -e "./configure" ]] && ./autogen.sh || ./config.status
  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/$pkgname-$pkgname-$pkgver"
  make DESTDIR="$pkgdir/" install
}

# vim:set ts=2 sw=2 et:
