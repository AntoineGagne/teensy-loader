pkgbase=teensy-loader
pkgname=teensy-loader
pkgver=1.40
pkgrel=1
url='https://www.pjrc.com/teensy/index.html'
arch=('any')
pkgdesc='Tool used to flash on Ergodox EZ'
license=('unknown')
depends=()
source=("https://www.pjrc.com/teensy/teensy_linux64.tar.gz" \
        "https://www.pjrc.com/teensy/49-teensy.rules")
sha256sums=('b4e26c4717afae5dee397fa3a0660a3e499e573e5edab259c5fd52beb221032e' \
            '031de0b26991b5a3b19c497d9c0a17f86c40c55d925b9d07d19ab89f2286469d')

package() {
    install -d "${pkgdir}"/{opt/${pkgname}/,usr,etc}
    install -d "${pkgdir}/opt/${pkgname}/bin"
    install -d "${pkgdir}/usr/bin"
    install -d "${pkgdir}/etc/udev/rules.d"

    mv ../49-teensy.rules "${pkgdir}/etc/udev/rules.d"
    mv "${srcdir}/"{libpng12.so.0,libusb-0.1.so.4,teensy} "${pkgdir}/opt/${pkgname}/bin"

    ln -s "/opt/${pkgname}/bin/teensy" "${pkgdir}/usr/bin/teensy"
}
