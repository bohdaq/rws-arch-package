# Maintainer: Bohdan Tsap <bohdan.tsap@tutanota.com>
pkgname=rust-web-server
binname=rws
pkgver=8.0.5
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
sha512sums=('c0b945a1a48016dc0505e06b1802248986a4cd6c73c3917ab299d9b0a73cf5758936ddba09c1d3cb1d23bc8fe0afe6c107aaf459d2b7625598919e1e6b2c6b92')
noextract=()
validpgpkeys=()

prepare() {
	cd $pkgname-$pkgver
	cargo fetch --offline --target "$CARCH-unknown-linux-gnu"	
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
