# Maintainer: Jesse Jaara <gmail.com: jesse.jaara>

pkgname=webvideo
pkgver=0.4.9
pkgrel=1
pkgdesc="Video download manager for Finnish tv chanels and youtube."
arch=('i686' 'x86_64')
url="http://users.tkk.fi/~aajanki/vdr/webvideo/"
license=('GPL3')
depends=('python-pycurl' 'yle-dl' 'mimms')
source=(http://projects.vdr-developer.org/attachments/download/1057/vdr-webvideo-${pkgver}.tgz
	webvideo-arch.patch)

build() {
  cd "$srcdir/$pkgname-$pkgver"

  patch -p1 -i ../webvideo-arch.patch
  make libwebvi
}

package() {
  cd "$srcdir/$pkgname-$pkgver"

  make DESTDIR="$pkgdir/" install-webvi
  mkdir "$pkgdir/etc"
  cp webvi.conf "$pkgdir/etc/"
}

md5sums=('3330d0256dcdc766a04e74ebf794dff9'
         '5bd4ddfdbf4fa04a1611f68820084dc8')
