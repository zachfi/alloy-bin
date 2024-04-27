# Maintainer: Zach Leslie <@zachfi>

pkgname=alloy-bin
_realname=alloy
pkgver=1.0.0
pkgrel=1
pkgdesc='A Kubernetes controller to manage nodes'
url="https://github.com/grafana/$_realname"
arch=(aarch64 armv7h x86_64)
license=('APACHE')
source_x86_64=("https://github.com/grafana/${_realname}/releases/download/v${pkgver}/${_realname}-linux-amd64.zip")
source_aarch64=("https://github.com/grafana/${_realname}/releases/download/v${pkgver}/${_realname}-linux-arm64.zip")
#sha256sums=('fa2edae90c7999a6f667bba26a6c63c7165647f77c02c83860237c6d08ee4bbd')
sha256sums_aarch64=('35b977a77ca9ac2ce4b5a57ce1d8d94e68976e57de3451db6eb88b0cc6d19643')
sha256sums_x86_64=('c926b29ed75d37b1bb2945a70f8f3e580b9f6192467ff956e3bbf52b70ad7321')

package() {
	case "$CARCH" in
	aarch64)
		_pkgarch="arm64"
		;;
	x86_64)
		_pkgarch="amd64"
		;;
	esac

	install -Dm755 "${_realname}-linux-${_pkgarch}" "${pkgdir}/usr/bin/${_realname}"
	install -Dm644 ${startdir}/alloy.service "${pkgdir}/usr/lib/systemd/system/alloy.service"
}
