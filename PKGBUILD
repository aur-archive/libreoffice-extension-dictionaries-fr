# Maintainer: Gilrain <gilrain+libre.arch A_T castelmo DOT_ re>

pkgname=libreoffice-extension-dictionaries-fr
pkgver=5.3
_pkgver=${pkgver//./-}
pkgrel=1
pkgdesc="French dictionaries for LibreOffice."
arch=('any')
url="http://extensions.libreoffice.org/extension-center/dictionnaires-francais/"
license=('custom:MPL2' 'LGPL')
depends=('libreoffice')
groups=('libreoffice-extensions')
makedepends=('unzip')
changelog=changelog
source=("http://extensions.libreoffice.org/extension-center/dictionnaires-francais/releases/${pkgver}/lo-oo-ressources-linguistiques-fr-v${_pkgver}.oxt"
	"https://www.mozilla.org/MPL/2.0/index.txt")
noextract=(lo-oo-ressources-linguistiques-fr-v${_pkgver}.oxt)
sha256sums=('6c30add1f8db661beac941053db11613ee55cec504c68a1639a6a040838d9cd3'
            'fab3dd6bdab226f1c08630b1dd917e11fcb4ec5e1e020e2c16f83a0a13863e85')

package() {
  install -dm755 ${pkgdir}/usr/lib/libreoffice/share/extensions
  unzip -q ${srcdir}/lo-oo-ressources-linguistiques-fr-v${_pkgver}.oxt -d ${pkgdir}/usr/lib/libreoffice/share/extensions/dict-fr/

  # fix world writable bit
  find "${pkgdir}/usr/lib/libreoffice/share/extensions/dict-fr/" \( -type d -exec chmod 755 {} \; \) -o \( -type f -exec chmod 644 {} \; \)

  install -Dm644 index.txt ${pkgdir}/usr/share/licenses/${pkgname}/LICENSE
}
