# Arch repos

## Adding the repos

Run the following commands:

```bash
doas pacman-key --keyserver hkps://keys.openpgp.org/ --recv-keys '72CA153D0D0A6824'
doas pacman-key --lsign-key '72CA153D0D0A6824'
```

Add these lines to `/etc/pacman.conf`:

```bash
[cactus]
Server = https://arch.gavrois.fr/$repo/os/$arch
```

## Installing wine

Use the following commands:
```bash
doas pacman -S wine-cactus dxvk-winelib vkd3d-winelib
winedxvk install --symlink # With or without WINEPREFIX
winevkd3d install --symlink # With or without WINEPREFIX
```

## Installing xow

Use the following commands:
```bash
doas pacman -S xow
doas systemctl enable xow
doas systemctl start xow
```

Do not use `libusb` on version 1.0.24-2.
