## Maintainer: peerchemist

pkgname='nubits-wallet'
pkgver=1.0.1
pkgrel=1
pkgdesc="The World's First Stable Digital Currency."
arch=('x86_64' 'i686')
url="https://nubits.com/"
license=('custom')
provides=('nubits-wallet')
depends=('qt4' 'miniupnpc' 'boost-libs' 'qrencode')
source=(https://nubits.com/sites/default/files/assets/nu-$pkgver-linux-gitian.zip
		https://nubits.com/sites/default/files/assets/logo-nu-full-150-dark.png
        'nu.desktop')
install=nu.install
sha256sums=('27b46cec192633f4e7bbdbeab4090fdb45d9ad484ad46125412698460d5653e8'
            '4500ea60a521a2df38ebe5c4d494e28036869c910b8414d9442900ace374d16b'
            '20977ea565836178b2c5aa8ff23964f097a68e3dec024074b702f11a46934479')

package() {

	install -Dm644 nu.desktop ${pkgdir}/usr/share/applications/nu.desktop
	install -Dm644 logo-nu-full-150-dark.png ${pkgdir}/usr/share/pixmaps/nu.png

	cd bin

	if [ "$CARCH" == "i686" ]; then
		install -Dm755 32/nu ${pkgdir}/usr/bin/nu
		install -Dm755 32/nud ${pkgdir}/usr/bin/nud
	
	elif [ "$CARCH" == "x86_64" ]; then
		install -Dm755 64/nu ${pkgdir}/usr/bin/nu
		install -Dm755 64/nud ${pkgdir}/usr/bin/nud

	fi
}

