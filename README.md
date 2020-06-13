## Void Linux template file for xbps-src

Instructions for building `picom-ibhagwan` on void linux using `xbps-src`:

1. Setup the `void-packages` repo:

```sh
❯ git clone --depth=1 https://github.com/void-linux/void-packages
❯ cd void-packages
❯ ./xbps-src binary-bootstrap
❯ echo XBPS_ALLOW_RESTRICTED=yes >> etc/conf
```

2. Download the template repo and copy into `srcpkgs`:

```sh
❯ git clone https://github.com/ibhagwan/picom-ibhagwan-template
❯ mv picom-ibhagwan-template ./srcpkgs/picom-ibhagwan
```

3. Build & install the package:

```sh
❯ ./xbps-src pkg picom-ibhagwan
❯ sudo xbps-install --repository=hostdir/binpkgs picom-ibhagwan 
```

**Note #1:** if you have `xtools` installed you can install the package by running `xi -f picom-ibhagwan` (instead of using `xbps-install`).

**Note #2:** before installing the package make sure to remove all other `compton|picom` packages with `sudo xbps-remove picom && sudo xbps-remove compton`.
