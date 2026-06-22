# Maintainer: tunnelpojken
pkgname=magi-anime
pkgver=1.1.6
pkgrel=1
pkgdesc="Anime terminal app powered by anipy-api"
arch=('x86_64')
url="https://github.com/tunnelpojken/magi-anime"
license=('MIT')
depends=('gtk3' 'util-linux-libs' 'xz')
source=("$pkgname-$pkgver.tar.gz::https://github.com/tunnelpojken/magi-anime/releases/download/v$pkgver/magi_anime-$pkgver-linux-x64.tar.gz")
sha256sums=('933e9cb27c2498829f5af88587bf5d872a5b74e9af9708941b6c657eb06354ee')

package() {
    install -dm755 "$pkgdir/opt/magi-anime"
    cp -r "$srcdir/bundle/." "$pkgdir/opt/magi-anime/"
    chmod +x "$pkgdir/opt/magi-anime/magi_anime"

    install -dm755 "$pkgdir/usr/bin"
    ln -s /opt/magi-anime/magi_anime "$pkgdir/usr/bin/magi-anime"

    install -dm755 "$pkgdir/usr/share/applications"
    cat > "$pkgdir/usr/share/applications/magi-anime.desktop" << EOF
[Desktop Entry]
Name=MAGI
Comment=Anime Terminal
Exec=/opt/magi-anime/magi_anime
Icon=magi-anime
Type=Application
Categories=AudioVideo;Video;
StartupWMClass=magi_anime
EOF
}
