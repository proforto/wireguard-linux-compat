# WireGuard for Linux 3.10 - 5.5

WireGuard was merged into the Linux kernel for 5.6. This repository contains a backport of WireGuard for kernels 3.10 to 5.5, as an out of tree module.

**More information may be found at [WireGuard.com](https://www.wireguard.com/).**

## License

This project is released under the [GPLv2](COPYING).

## Build on Ubuntu
- https://www.wireguard.com/compilation/
- https://www.reddit.com/r/WireGuard/comments/h0tkzt/up_to_date_ubuntu_18044_cannot_compile_wireguard/

```
# Install toolchain
sudo apt-get install libelf-dev linux-headers-$(uname -r) build-essential pkg-config

cd /tmp

# Grab the code
git clone https://github.com/proforto/wireguard-linux-compat.git
git clone https://git.zx2c4.com/wireguard-tools

# Compile and install module
make -C wireguard-linux-compat/src -j$(nproc)
sudo make -C wireguard-linux-compat/src install

# Compile and install the wg tool
make -C wireguard-tools/src -j$(nproc)
sudo make -C wireguard-tools/src install
```
