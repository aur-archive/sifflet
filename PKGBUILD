# custom variables
_hkgname=sifflet
_licensefile=LICENSE

# PKGBUILD options/directives
pkgname=sifflet
pkgver=1.2.4
pkgrel=24
pkgdesc="A simple, visual, functional programming language."
url="http://mypage.iu.edu/~gdweber/software/sifflet/"
license=("BSD3")
arch=('i686' 'x86_64')
makedepends=("ghc=7.0.3-2"
             "haskell-cairo=0.12.1-2"
             "haskell-fgl=5.4.2.3-4.1"
             "haskell-glib=0.12.1-2"
             "haskell-gtk=0.12.1-2"
             "haskell-hxt=9.1.4-2"
             "haskell-mtl=2.0.1.0-3.1"
             "haskell-sifflet-lib=1.2.4-24"
             "haskell-unix=2.4.2.0-2")
depends=()
options=('strip')
source=("http://hackage.haskell.org/packages/archive/${_hkgname}/${pkgver}/${_hkgname}-${pkgver}.tar.gz")

sha256sums=("5b0c1d3b434b8cf49d166518f1647300c54a4bc904ad4397fdbe2dc28cac4acf")

# PKGBUILD functions
build() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    
    runhaskell Setup configure -O --prefix=/usr --docdir=/usr/share/doc/${pkgname}
    runhaskell Setup build
}

package() {
    cd ${srcdir}/${_hkgname}-${pkgver}
    runhaskell Setup copy --destdir=${pkgdir}
}
