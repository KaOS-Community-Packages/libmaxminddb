pkgname=libmaxminddb
pkgver=1.4.2
pkgrel=1
pkgdesc="MMaxMindDB GeoIP2 database library"
license=('Apache')
arch=('x86_64')
url="https://dev.maxmind.com/geoip/geoip2/downloadable/"
depends=('glibc')
optdepends=('geoip-database: IP geolocation databases')
source=("https://github.com/maxmind/libmaxminddb/releases/download/$pkgver/libmaxminddb-$pkgver.tar.gz")
sha256sums=('dd582aa971be23dee960ec33c67fb5fd38affba508e6f00ea75959dbd5aad156')

check() {
	cd "$srcdir"/libmaxminddb-$pkgver
	make check
}

build() {
	cd "$srcdir"/libmaxminddb-$pkgver
	./configure --prefix=/usr
	make
}

package() {
	cd "$srcdir"/libmaxminddb-$pkgver
	make PREFIX=/usr DESTDIR="$pkgdir" install
	rm -rf "$pkgdir"/usr/{bin,share/man/man1}
}
