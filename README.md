Packages for the ThinkPad X13s

## Binary repository
To use pre-built packages, add this section to the end of your `/etc/pacman.conf`:

```conf
[x13s-alarm]
Server = https://ericsandu.github.io/x13s-alarm/
```

You'll need to trust the public key in order to verify package signature:

```bash
sudo pacman-key --recv-keys A7A1CBA34B419028
sudo pacman-key --lsign-key A7A1CBA34B419028
```

if it still says "unknown trust" even after you lsign it, try this and then resign:
```bash
sudo rm -rf /etc/pacman.d/gnupg
sudo pacman-key --init
sudo pacman-key --populate archlinux
sudo pacman-key --populate archlinuxarm
```

## Note on `linux-x13s`
For now, you will need `efi=noruntime clk_ignore_unused pd_ignore_unused arm64.nopauth` as kernel parameters to boot into the kernel.
