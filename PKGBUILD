# Maintainer: tunnelpojken
pkgname=magi-anime
pkgver=1.3.10
pkgrel=1
pkgdesc="Anime terminal app powered by anipy-api"
arch=('x86_64')
url="https://github.com/tunnelpojken/magi-anime"
license=('MIT')
depends=('gtk3' 'util-linux-libs' 'xz')
source=("$pkgname-$pkgver.tar.gz::https://github.com/tunnelpojken/magi-anime/releases/download/v$pkgver/magi_anime-$pkgver-linux-x64.tar.gz")
sha256sums=('32c6537803647b5232d979a3f3a6aa1c3da8b8550e59281df03f6120934f24f4')

package() {
    install -dm755 "$pkgdir/opt/magi-anime"
    cp -r "$srcdir/bundle/." "$pkgdir/opt/magi-anime/"
    chmod +x "$pkgdir/opt/magi-anime/magi_anime"

    install -Dm644 "$srcdir/bundle/data/flutter_assets/assets/icon.png" \
    "$pkgdir/usr/share/pixmaps/magi-anime.png"

    install -dm755 "$pkgdir/usr/bin"
    ln -s /opt/magi-anime/magi_anime "$pkgdir/usr/bin/magi-anime"

    install -dm755 "$pkgdir/usr/share/applications"
    cat > "$pkgdir/usr/share/applications/magi-anime.desktop" << EOF
[Desktop Entry]
Name=MAGI
Comment=Anime Terminal
Exec=/opt/magi-anime/magi_anime --enable-software-rendering
Icon=magi-anime
Type=Application
Categories=AudioVideo;Video;
StartupWMClass=magi_anime
EOF
}
