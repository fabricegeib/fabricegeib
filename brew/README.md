# Brew

```
❯ brew outdated
c-ares (1.17.1) < 1.18.1_1
curl (7.74.0) < 7.82.0
gdbm (1.18.1, 1.18.1_1) < 1.23
icu4c (67.1) < 70.1
libidn2 (2.3.0) < 2.3.2
libssh2 (1.9.0_1) < 1.10.0
libunistring (0.9.10) < 1.0
ncurses (6.1_1) < 6.3
nghttp2 (1.42.0_1) < 1.47.0
node (15.4.0) < 17.8.0
openldap (2.4.56) < 2.6.1
openssl@1.1 (1.1.1g, 1.1.1i) < 1.1.1n
pcre (8.43) < 8.45
python@3.9 (3.9.0_5) < 3.9.12
readline (8.0.4, 8.1) < 8.1.2
ruby (2.7.2) < 3.1.1
teamookla/speedtest/speedtest (1.0.0) < 1.1.1.84
sqlite (3.31.1, 3.34.0) < 3.38.2
wget (1.20.3_2) < 1.21.3
yarn (1.22.10) < 1.22.18
zsh (5.7.1) < 5.8.1
zstd (1.4.5) < 1.5.2
bluestacks (4.160.10.2058,1758593b86f4809a6c06f6b402b1c121) != 4.270.1.2803,c610c2d26a70cad789a74e586a08e51f
chrome-remote-desktop-host (latest) != 89.0.4389.25
gemini (2.5.7,333:1570627795) != 2.9.4,391,1645434880
impactor (0.9.52) != 0.9.56
keyboardcleantool (latest) != 3
kitematic (0.17.11) != 0.17.13
nextcloud (2.6.3.20200217) != 3.4.4
onyx (3.7.3) != 3.8.7
virtualbox (6.1.4,136177) != 6.1.32,149290
```

```brew upgrade````

```
Error: Could not symlink Frameworks/Python.framework/Versions/3.9/Headers
Target /usr/local/Frameworks/Python.framework/Versions/3.9/Headers
is a symlink belonging to python@3.9. You can unlink it:
  brew unlink python@3.9

To force the link and overwrite all conflicting files:
  brew link --overwrite python@3.9

To list all files that would be deleted:
  brew link --overwrite --dry-run python@3.9

```

```
❯ brew unlink python@3.9
Unlinking /usr/local/Cellar/python@3.9/3.9.12... 0 symlinks removed.
```
