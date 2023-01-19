# Maintainer: Bohdan Tsap <bohdan.tsap@tutanota.com>
pkgname=rust-web-server
binname=rws
pkgver=9.0.0
pkgrel=1
epoch=
pkgdesc="Static content web-server written in Rust"
arch=('x86_64')
url="https://github.com/bohdaq/rust-web-server"
license=('MIT' 'APACHE' 'ISC' 'CC-BY-4.0' 'LGPL-3.0')
groups=()
depends=()
makedepends=(cargo)
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=("$pkgname-$pkgver.tar.gz::https://github.com/bohdaq/$pkgname/archive/$pkgver.tar.gz")
sha256sums=('9d67f2e53798def27ce3c9bec3d4d290f2e241afcd48664616f2df0a20b3b374')
noextract=()
validpgpkeys=()

prepare() {
	cd $pkgname-$pkgver
	cargo fetch --target "$CARCH-unknown-linux-gnu"
}

build() {
	cd $pkgname-$pkgver
	export RUSTUP_TOOLCHAIN=stable
	export CARGO_TARGET_DIR=target
	cargo build --frozen --release --all-features
}

check() {
	cd $pkgname-$pkgver
	export RUST_TOOLCHAIN=stable
	cargo test --frozen --all-features
}

package() {
	cd $pkgname-$pkgver
	install -Dm0755 -t "$pkgdir/usr/bin" "target/release/$binname"
}
