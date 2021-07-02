# Arch repos

## Adding the repos

Run the following commands:

```bash
doas pacman-key --keyserver hkps://keys.openpgp.org/ --recv-keys '72CA153D0D0A6824'
doas pacman-key --lsign-key '72CA153D0D0A6824'
```

Add these lines to `/etc/pacman.conf`:

```bash
[gavrois]
Server = https://arch.gavrois.fr/$arch
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
