repro
=====

The goal is to create a tool that can easily verify Arch Linux packages for reproducability.

The current goals are:
- Build package N times with environment changes to check for reproducability
- Recreate packages given `.BUILDINFO` file

Work in progress. Please read the code file before using.


```
$ repro
==> Using SOURCE_DATE_EPOCH: 1513029322
:: Synchronizing package databases...
 core is up to date
 extra is up to date
 community is up to date
 pacman is up to date
:: Starting full system upgrade...
 there is nothing to do
==> Starting build1...
  -> Create snapshot for build1...
  -> Creating rsync snapshot
==> Making package: archlinux-keyring 20171020-1 (Mon Dec 11 22:55:31 CET 2017)
==> Checking runtime dependencies...
==> Checking buildtime dependencies...
==> Retrieving sources...
  -> Found archlinux-keyring-20171020.tar.gz
  -> Found archlinux-keyring-20171020.tar.gz.sig
==> Validating source files with sha256sums...
    archlinux-keyring-20171020.tar.gz ... Passed
    archlinux-keyring-20171020.tar.gz.sig ... Skipped
==> Verifying source file signatures with gpg...
    archlinux-keyring-20171020.tar.gz ...
==> Extracting sources...
  -> Extracting archlinux-keyring-20171020.tar.gz with bsdtar
==> Entering fakeroot environment...
==> Starting package()...
install -dm755 /startdir/pkg/archlinux-keyring/usr/share/pacman/keyrings/
install -m0644 archlinux{.gpg,-trusted,-revoked} /startdir/pkg/archlinux-keyring/usr/share/pacman/keyrings/
==> Tidying install...
  -> Removing libtool files...
  -> Purging unwanted files...
  -> Removing static library files...
  -> Stripping unneeded symbols from binaries and libraries...
  -> Compressing man and info pages...
==> Checking for packaging issues...
==> Creating package "archlinux-keyring"...
  -> Generating .PKGINFO file...
  -> Generating .BUILDINFO file...
  -> Adding install file...
  -> Generating .MTREE file...
  -> Compressing package...
==> Leaving fakeroot environment.
==> Signing package(s)...
==> Finished making: archlinux-keyring 20171020-1 (Mon Dec 11 22:55:32 CET 2017)
==> Cleaning up...
  -> Delete snapshot for build1...
==> Starting build2...
  -> Create snapshot for build2...
  -> Creating rsync snapshot
==> Making package: archlinux-keyring 20171020-1 (Mon Dec 11 22:55:44 CET 2017)
==> Checking runtime dependencies...
==> Checking buildtime dependencies...
==> Retrieving sources...
  -> Found archlinux-keyring-20171020.tar.gz
  -> Found archlinux-keyring-20171020.tar.gz.sig
==> Validating source files with sha256sums...
    archlinux-keyring-20171020.tar.gz ... Passed
    archlinux-keyring-20171020.tar.gz.sig ... Skipped
==> Verifying source file signatures with gpg...
    archlinux-keyring-20171020.tar.gz ... 
==> Extracting sources...
  -> Extracting archlinux-keyring-20171020.tar.gz with bsdtar
==> Entering fakeroot environment...
==> Starting package()...
install -dm755 /startdir/pkg/archlinux-keyring/usr/share/pacman/keyrings/
install -m0644 archlinux{.gpg,-trusted,-revoked} /startdir/pkg/archlinux-keyring/usr/share/pacman/keyrings/
==> Tidying install...
  -> Removing libtool files...
  -> Purging unwanted files...
  -> Removing static library files...
  -> Stripping unneeded symbols from binaries and libraries...
  -> Compressing man and info pages...
==> Checking for packaging issues...
==> Creating package "archlinux-keyring"...
  -> Generating .PKGINFO file...
  -> Generating .BUILDINFO file...
  -> Adding install file...
  -> Generating .MTREE file...
  -> Compressing package...
==> Leaving fakeroot environment.
==> Signing package(s)...
==> Finished making: archlinux-keyring 20171020-1 (Mon Dec 11 22:55:45 CET 2017)
==> Cleaning up...
  -> Delete snapshot for build2...
==> Comparing hashes...
  -> archlinux-keyring-20171020-1-any.pkg.tar.xz is reproducible!
==> Package is reproducible!