# Maintainer: Jose C.

pkgname=jetbrains-datagrip
pkgver=2021.3.4
pkgrel=1
pkgdesc="IDE that is tailored to suit the specific needs of professional SQL developers."
arch=('x86_64')
options=('!strip')
url="https://www.jetbrains.com/datagrip/"
license=('Commercial')
provides=('datagrip')
conflicts=('datagrip')

_filename="datagrip-$pkgver.tar.gz"
_filextract="DataGrip-$pkgver"

source=("https://download.jetbrains.com/datagrip/datagrip-$pkgver.tar.gz"
	"${pkgname}.desktop")

sha256sums=( 'a34670f1a6c77e00237302a70f22fb5bf089dfe128341fd89b2f25bb8becb325'
'a437f7fd7cf27e8e1129c62916c40d4e39de4e68d9c98321fb8c61cf2b28011a')

package() {
	#Create directories with permission rwxr-xr-x
	install -m755 -d "${pkgdir}/usr/share" "${pkgdir}/usr/bin" "${pkgdir}/usr/share/applications"

	#Copy files to pkg destination
	cp -r "${srcdir}/${_filextract}" "${pkgdir}/usr/share/${pkgname}"
  chown -R root:root "${pkgdir}/usr/share/${pkgname}"

	ln -s "/usr/share/${pkgname}/bin/datagrip.sh" "${pkgdir}/usr/bin/datagrip"
  install -m644 "${srcdir}/${pkgname}.desktop" "${pkgdir}/usr/share/applications"
}
