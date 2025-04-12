# Maintainer: Your Name <your@email.com>
pkgname=illustrator-cc-wine
pkgver=17
pkgrel=1
pkgdesc="Adobe Illustrator CC 2017 (v17) for Linux using Wine"
arch=('x86_64')
url="https://www.adobe.com/products/illustrator.html"
license=('custom')
depends=('wine' 'winetricks' 'zenity' 'p7zip' 'lib32-gnutls' 'lib32-alsa-lib' 'lib32-libpulse')
source=("illustratorCC17.tgz::https://downloads.runebase.io/illustratorCC17.tgz"
        "illustrator.desktop"
        "illustrator.png")  
sha256sums=('SKIP'
            'SKIP'
            'SKIP') # Replace with desktop checksum

package() {
  # ----- Create Directory Structure -----
  install -dm755 "$pkgdir/opt/illustratorCC"
  install -dm755 "$pkgdir/usr/bin"
  install -Dm644 "$srcdir/illustrator.png" "$pkgdir/opt/illustratorCC/illustrator.png"

  # ----- Extract Main Files -----
  tar -xzf "$srcdir/illustratorCC17.tgz" -C "$pkgdir/opt/illustratorCC"

  # ----- Create Wine Prefix Directory -----
  install -dm755 "$pkgdir/opt/illustratorCC/prefix"

  # ----- Install Desktop File -----
  install -Dm644 "$srcdir/illustrator.desktop" \
    "$pkgdir/usr/share/applications/illustrator.desktop"

  # ----- Create Launcher -----
  cat > "$pkgdir/usr/bin/illustrator-cc" << 'EOF'
#!/bin/bash
export WINEPREFIX="/opt/illustratorCC/prefix"
export WINEARCH="win64"
exec wine "/opt/illustratorCC/illustratorCC17/IllustratorCC64.exe" "$@"
EOF
  chmod 755 "$pkgdir/usr/bin/illustrator-cc"
}

post_install() {
  echo "Fixing directory permissions..."
  export WINEPREFIX="/opt/illustratorCC/prefix"
  export WINEARCH="win64"
  
  # Fix ownership
  chown -R $USER:$USER "/opt/illustratorCC"
  
  # Initialize Wine
  wineboot -u &>/dev/null
  winetricks -q corefonts vcrun2013 &>/dev/null
  
  # Apply dark mode
  [ -f "$WINEPREFIX/user.reg" ] && sed -i \
    -e 's/"Theme"=".*"/"Theme"="Yaru"/' \
    -e 's/"ColorScheme"=".*"/"ColorScheme"="Yaru"/' \
    "$WINEPREFIX/user.reg"

  echo -e "\n\033[1;32mReady to use!\033[0m\nRun: illustrator-cc"
}

post_upgrade() {
  post_install
}