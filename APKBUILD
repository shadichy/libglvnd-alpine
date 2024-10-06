# Contributor: Shadichy <shadichy.dev@gmail.com>
pkgname=libglvnd
pkgver=1.7.0
pkgrel=1
arch="all !armhf !ppc64le !s390x !riscv64"
url="https://gitlab.freedesktop.org/glvnd/libglvnd"
pkgdesc="Distribution-independent installer framework"
license="custom:BSD-like"
source="https://gitlab.freedesktop.org/-/project/4399/uploads/c24806c283070dc70700234ca8ffacf8/libglvnd-1.7.0.tar.gz"
subpackages="$pkgname-dev"
provides="mesa-egl mesa-gl mesa-gles mesa-dev"

build() {
  meson setup \
    --prefix /usr \
    --libexecdir lib \
    --sbindir bin \
    --buildtype plain \
    --auto-features enabled \
    --wrap-mode nodownload \
    -D b_pie=true \
    -D python.bytecompile=1 \
    -D gles1=false \
    build
    meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"
}

sha512sums="
185a3a65eb31fe93920b10d9d61de3c0a156c8813acca9a6596096342f527172ac6d8eed581ce2a1a4ac548d59ff25120a6d95f73ad90f26a02e3c30eb84f6c1  libglvnd-1.7.0.tar.gz
"
