# Maintainer: Philipp Kiersch <philippkiersch at gmail dot com>
# Contributor: Sam Stuewe <halosghost at archlinux dot info>
# Contributor: Scimmia
# Contributor: WorMzy
pkgname=iscan-plugin-gt-1500
pkgver=2.2.0_1
pkgrel=2
pkgdesc="iscan plugin for the Epson GT-1500 scanner."
arch=('i686' 'x86_64')
url="http://download.ebz.epson.net/dsc/search/01/search/?OSC=LX"
license=('custom')
depends=('iscan' 'iscan-data')
install=gt-1500.install

if [[ "$CARCH" == "i686" ]]; then
   _srcurl="http://download.ebz.epson.net/dsc/f/01/00/02/09/21/79a6200fed4b7bd1c0ce04909e1a4f64e854b9fb"
   sha256sums=('cbb3e7855b9d119aca3070777076d461125de9b907822a1d3fa4669b10cb6514')
elif [[ "$CARCH" == "x86_64" ]]; then
   _srcurl="http://download.ebz.epson.net/dsc/f/01/00/02/09/21/89f74a7055d4c0fd8c7842a212e80f534b957bfa"
   sha256sums=('f5e3efa4e739b80e87443b1b1124c79036ef7ed684d8d5f58f5ce4e5754516db')
fi
source=("$_srcurl/${pkgname}-${pkgver//_/-}.${CARCH//i686/i386}.rpm"        
"gt-1500.install")
sha256sums+=('bcaa2139106cc7f3049008925de32e5f2c91f41dbdeba6bc5c9f65ae424efe26')

package() {
  cd "$srcdir"
  cp -dpr --no-preserve=ownership usr "$pkgdir"
  install -Dm644 "${pkgdir}/usr/share/doc/${pkgname}-${pkgver//_1/}/AVASYSPL.en.txt" "${pkgdir}/usr/share/licenses/${pkgname}/AVASYSPL.en.txt"
  rm -r "$pkgdir"/usr/share/doc
}

