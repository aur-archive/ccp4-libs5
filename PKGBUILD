# Maintainer: Alexander Minges <alexander.minges@gmail.com>
pkgname=ccp4-libs5
pkgver=5.0.2
pkgrel=2
pkgdesc="Protein X-ray crystallography toolkit - Libraries"
arch=('i686' 'x86_64')
url="http://www.ccp4.ac.uk/"
license=('GPL')
provides=('ccp4-libs=5.0.2')
conflicts=('ccp4-libs6')
_url="http://www2.mrc-lmb.cam.ac.uk/personal/pemsley/coot/dependencies"
source=(${_url}/libccp4c-$pkgver-ysbl-3.tar.gz
        ${_url}/martyn-extras.tar.gz
        ${_url}/${pkgname/5}-underlay-2.tar.gz)
sha256sums=('536c65fe1603e1007891bb56e99a2222a317fe840ed354fb7d3ec35a6bff6ffe'
            '06b91788295f9ccd25a22a58966fdf814a7a7ce3f00521a365d642f906dcb83a'
            '6ac71bc416810cc358c311a92f6eceea5549556ca57f9cad104c950840c0c954')
noextract=(martyn-extras.tar.gz
           ${pkgname/5}-underlay-2.tar.gz)

build() {
  cd "$srcdir/libccp4c-5.0.2-ysbl-3"
  
  gzip -dc ${srcdir}/ccp4-libs-underlay-2.tar.gz | tar xf -
  gzip -dc ${srcdir}/martyn-extras.tar.gz | tar xf -

  ./configure --prefix=/usr
  make
}

package() {
  cd "$srcdir/libccp4c-5.0.2-ysbl-3"

  make DESTDIR="$pkgdir/" install
} 
