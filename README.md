# Arch repos

## Adding the repos

Run the following commands:

```bash
pacman-key --keyserver hkps://keys.openpgp.org/ --recv-keys '72CA153D0D0A6824'
pacman-key --lsign-key '72CA153D0D0A6824'
```

Add these lines to `/etc/pacman.conf`:

```bash
[cactus]
Server = https://arch.gavrois.fr/$repo/os/$arch
```

## Installing wine

Use the following commands:
```bash
pacman -S wine-cactus
```

## Installing xow

Use the following commands:
```bash
pacman -S xow
systemctl enable xow
systemctl start xow
```

Do not use `libusb` on version 1.0.24-2.
