# Maintainer: Julius Schumacher <juliusschumacher@gmail.com>
basepkgname=erlang_ls
pkgname="${basepkgname}-git"
pkgver=0.20.0.r83.d499966
pkgrel=1
pkgdesc="Erlang Language Server Protocol Implementation"
arch=(x86_64)
url="https://github.com/erlang-ls/erlang_ls"
license=('Apache')
depends=(erlang rebar3)
makedepends=('git')
provides=($basepkgname)
conflicts=($basepkgname)
source=("git+$url")
noextract=()
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/$basepkgname"
	git describe --long --tags | sed 's/\([^-]*-\)g/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/$basepkgname"
	make
}

package() {
	install -Dm755 \
		"$srcdir/${pkgname%-git}/_build/default/bin/erlang_ls" \
		"$pkgdir/usr/bin/erlang_ls"

}
