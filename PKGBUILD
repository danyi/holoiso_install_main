pkgname=holoiso-main
pkgver="snapshot_beta$(date +%Y%m%d.%H%M)"
pkgdesc="HoloISO base installation (Beta branch)"
pkgrel="1"
depends=('archlinux-keyring' 'ark' 'cheese' 'chromium' 'cups' 'curl' 'dolphin' 'ffmpegthumbs' 'gamescope' 'git' 'glxinfo' 'go' 'gwenview' 'hunspell' 'hunspell-en_us' 'jupiter-hw-support' 'kdegraphics-thumbnailers' 'konsole' 'kwrite' 'lib32-pipewire' 'lib32-pipewire-jack' 'lib32-pipewire-v4l2' 'lib32-vulkan-radeon' 'mangohud' 'holoiso-updateclient' 'noto-fonts-cjk' 'pipewire' 'pipewire-alsa' 'pipewire-jack' 'wireplumber' 'pipewire-pulse' 'pipewire-v4l2' 'plasma-meta' 'plasma-nm' 'print-manager' 'spectacle' 'steam-jupiter-stable' 'steamdeck-kde-presets' 'tar' 'ufw' 'vlc' 'vulkan-radeon' 'yay' 'wget' 'zsh' 'xbindkeys')
arch=("x86_64")

package() {
    holoiso_basever="SteamOS_Holo-$(date +%Y%m%d_%H%M)_Stable-x86_64"
    holoiso_codename="2d97f46f021 (snapshot1)"
    mkdir -p "${pkgdir}/usr/bin"
    mkdir -p "${pkgdir}/etc"
    mkdir -p "${pkgdir}/etc/udev"    
    mkdir -p "${pkgdir}/etc/udev/rules.d"    
    mkdir -p "${pkgdir}/usr/lib/systemd/system" 
    cp "${srcdir}/99-oxpgamepad.rules" "${pkgdir}/etc/udev/rules.d/99-oxpgamepad.rules" 
    cp "${srcdir}/holoiso-reboot-tracker.service" "${pkgdir}/usr/lib/systemd/system/holoiso-reboot-tracker.service"       
    cp "${srcdir}/steamos-session-select" "${pkgdir}/usr/bin/steamos-session-select"
    cp "${srcdir}/holoiso-gamescope-power" "${pkgdir}/usr/bin/holoiso-gamescope-power"
    cp "${srcdir}/holoiso-reboot-tracker" "${pkgdir}/usr/bin/holoiso-reboot-tracker"
    cp "${srcdir}/jupiter-controller-update" "${pkgdir}/usr/bin/jupiter-controller-update"
    cp "${srcdir}/holoiso-disable-sessions" "${pkgdir}/usr/bin/holoiso-disable-sessions"  
    cp "${srcdir}/holoiso-enable-sessions" "${pkgdir}/usr/bin/holoiso-enable-sessions" 
    cp "${srcdir}/steamos-select-branch" "${pkgdir}/usr/bin/steamos-select-branch"
    cp "${srcdir}/recoveryinit" "${pkgdir}/usr/bin/recoveryinit"      
    cp "${srcdir}/osinfo" "${srcdir}/osinfo_tmp"
    cp "${srcdir}/pacman.conf" "${pkgdir}/etc/pacman.conf"
    sed -i "s/snapshotver/snapshot_beta$(date +%Y%m%d.%H%M)/g" osinfo_tmp
    sed -i "s/versionver/${holoiso_codename}/g" osinfo_tmp
    sed -i "s/buildver/${holoiso_basever}/g" osinfo_tmp
    cp "${srcdir}/osinfo_tmp" "${pkgdir}/etc/os-release"
    cp "${srcdir}/holoiso-branch" "${pkgdir}/etc/holoiso-branch"
    rm "${srcdir}/osinfo_tmp"
    chmod +x "${pkgdir}/usr/bin/steamos-session-select"
    chmod +x "${pkgdir}/usr/bin/jupiter-controller-update"   
    chmod +x "${pkgdir}/usr/bin/recoveryinit"  
    chmod +x "${pkgdir}/usr/bin/holoiso-reboot-tracker" 
    chmod +x "${pkgdir}/usr/bin/holoiso-gamescope-power"
    chmod +x "${pkgdir}/usr/bin/holoiso-disable-sessions"
    chmod +x "${pkgdir}/usr/bin/holoiso-enable-sessions"
    chmod +x "${pkgdir}/usr/bin/steamos-select-branch"
    chmod 0644 "${pkgdir}/usr/lib/systemd/system/holoiso-reboot-tracker.service"
}
