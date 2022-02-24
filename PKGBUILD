pkgname=st-git
pkgver=0.8.4.r.
pkgrel=1
pkgdesc="A heavily-patched and customized build of st the Suckless simple terminal from DistroTube."
arch=(x86_64)
url="https://github.com/msang2403/st.git"
license=('MIT')
groups=()
depends=()
makedepends=(git)
checkdepends=()
optdepends=()
provides=(st)
conflicts=(st)
replaces=()
backup=()
options=()
source=("git+$url")
noextract=()
md5sums=('SKIP')
validpgpkeys=()

pkgver() {
  cd "${_pkgname}"
  printf "0.8.4.r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

build() {
  cd st
  make X11INC=/usr/include/X11 X11LIB=/usr/lib/X11
}

package() {
  cd st  
  mkdir -p ${pkgdir}/opt/${pkgname}
  cp -rf * ${pkgdir}/opt/${pkgname}
  make PREFIX=/usr DESTDIR="${pkgdir}" install
  install -Dm644 LICENSE "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
  install -Dm644 README "${pkgdir}/usr/share/doc/${pkgname}/README"
}

