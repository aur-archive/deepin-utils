# Maintainer: 4679kun <admin[AT]4679.us>

pkgname=deepin-utils
pkgver=20140703165416~8aaf2a6f00
pkgrel=3
pkgdesc='Utils of DeepinUI Toolkit modules'
arch=('i686' 'x86_64')
depends=('python2' 'pygtk' 'python2-cairo' 'python2-imaging' 'libwebkit' 'python2-xlib' 'pywebkitgtk')
makedepends=('python2-setuptools')
url="http://www.linuxdeepin.com/"
license=('GPL3')
source=("http://packages.linuxdeepin.com/deepin/pool/main/d/deepin-utils/deepin-utils_0.0.2+${pkgver}.tar.gz")
md5sums=('b22f040e268fd4cc8fa2c7a1b34cbe8f')

build(){
	cd "$srcdir"/${pkgname}-0.0.2+${pkgver}/
	python2 setup.py build
}
package() {
	cd "$srcdir"/${pkgname}-0.0.2+${pkgver}/
	python2 setup.py install --root="$pkgdir/" --optimize=1
	
	cd ${pkgdir}/usr/lib/python2.7/site-packages/deepin_utils/
    sed -i 's_#! /usr/bin/env python$_#! /usr/bin/env python2_' *.py   
}
