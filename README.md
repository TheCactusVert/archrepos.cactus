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

## Installing wine-proton

Use the following commands:
```bash
doas pacman -S wine-proton dxvk-winelib vkd3d-winelib
winedxvk install --symlink # With or without WINEPREFIX
winevkd3d install --symlink # With or without WINEPREFIX
```

`wine-proton` is compiled only in 64 bits.
Use `wine64` to run your game (or app).

## Installing xow

Use the following commands:
```bash
doas pacman -S xow
doas systemctl enable xow
doas systemctl start xow
```

Do not use `libusb` on version 1.0.24-2.
