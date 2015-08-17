# Maintainer: Tianjiao Yin <ytj000@gmail.com>

pkgname=python-sphinx-contrib
pkgver=1004
pkgrel=2
pkgdesc="Contributed extensions for Sphinx (A python documentation generator)."
arch=("any")
url="https://bitbucket.org/birkenfeld/sphinx-contrib/"
license=('custom')
depends=("python2-sphinx")
makedepends=("mercurial")
provides=("sphinxcontrib-phpdomain")
conflicts=("sphinxcontrib-phpdomain")

_hgroot="https://bitbucket.org/birkenfeld"
_hgrepo="sphinx-contrib"
source=("setup.py")

_document_path="$pkgdir/usr/share/doc/python-sphinx-contrib"

build() {
    rm -rf build
    cp -rf "${_hgrepo}" build
    cd build
    hg checkout "${pkgver}"
}

package() {
    mkdir -p "$_document_path"
    python2 "$srcdir/setup.py" "$srcdir/build" "$pkgdir" "$_document_path"

    # remove conflict files with python-boto
    rm -rf "$pkgdir/usr/lib/python2.7/site-packages/tests/" 
}
md5sums=('45f1dad1c007ee17d1ce48d1c7063066')
