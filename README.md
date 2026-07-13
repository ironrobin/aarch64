Packages for the ThinkPad T14s

## Binary repository
To use pre-built packages, add this section to the end of your `/etc/pacman.conf`:

```conf
[ironrobin-aarch64]
Server = https://github.com/ironrobin/aarch64/releases/download/packages
```

You'll need to trust the public key in order to verify package signature:

```bash
sudo pacman-key --recv-keys 6ED02751500A833A
sudo pacman-key --lsign-key 6ED02751500A833A
```

if it still says "unknown trust" even after you lsign it, try this and then resign:
```bash
sudo rm -rf /etc/pacman.d/gnupg
sudo pacman-key --init
sudo pacman-key --populate archlinux
sudo pacman-key --populate archlinuxarm
```
