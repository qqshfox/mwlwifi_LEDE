# mwlwifi
Pre-compiled mwlwifi drivers for stable LEDE releases

I have decided to start following Linksys' official repo for the mwlwifi drivers, and make pre-compiled packages that can be installed on top of LEDE stable releases, so more people can test the latest commits and report bugs.

To install these packages on a stock LEDE installation, you can download the `.ipk` files with `wget url_to_package.ipk` then `opkg install --force-downgrade name_of_package.ipk`, or directly using `opkg install --force-downgrade url_to_package.ipk` (but then you need to have `libustream-openssl`, `ca-bundle` and `ca-certificates` packages installed, and use `http` instead of `https`).

As these packages do not follow a sequential numering, `opkg` will refuse to "update" them; you need to remove the previous `kmod-mwlwifi` package before installing a new one, or use the `--force-downgrade` parameter to `opkg`.

To revert to the stock version of mwlwifi you can do `opkg remove kmod-mwlwifi` then `opkg update` and `opkg install kmod-mwlwifi`.

* Files can be found at https://github.com/eduperez/mwlwifi_LEDE/releases.
* LEDE source code available at https://git.lede-project.org/?p=source.git
* mwlwifi drivers source code available at https://github.com/kaloz/mwlwifi
