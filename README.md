## HOW TO BUILD

```bash
git clone https://github.com/dur-randir/libtorrent.git && \
git clone https://github.com/rakshasa/rtorrent.git && \
cd libtorrent && \
./configure --enable-static --disable-shared --disable-debug --disable-backtrace --disable-instrumentation && \
make -j && \
cd ../rtorrent && \
CFLAGS=-O2 DEPENDENCIES_CFLAGS='-I/opt/libtorrent/src' DEPENDENCIES_LIBS='-L/opt/libtorrent/src /opt/libtorrent/src/.libs/libtorrent.a -lssl -lcrypto -lz'  ./configure --enable-debug=no && \
make -j && \
ls -al ./src/rtorrent
```


## LICENSE

Copyright (C) 2005-2014, Jari Sundell

 GNU GPL, see COPYING. "libtorrent/src/utils/sha_fast.{cc,h}" is
originally from the Mozilla NSS and is under a triple license; MPL,
LGPL and GPL. An exception to non-NSS code has been added for linking
to OpenSSL as requested by Debian, though the author considers that
library to be part of the Operative System and thus linking is allowed
according to the GPL.

 Use whatever fits your purpose, the code required to compile with
Mozilla's NSS implementation of SHA1 has been retained and can be
compiled if the user wishes to avoid using OpenSSL.
