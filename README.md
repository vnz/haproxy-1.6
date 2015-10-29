Haproxy build dependencies
==========================

* aptitude install -y libpcre3-dev zlib1g-dev libssl-dev

[Lua 5.3.x](http://www.lua.org/download.html) needed.
* aptitude install -y libtool libtool-bin libreadline-dev
* curl -R -O http://www.lua.org/ftp/lua-5.3.1.tar.gz
* tar zxf lua-5.3.1.tar.gz
* cd lua-5.3.1
* make linux test
* sudo make install


Build haproxy package
=====================

* debian/rules clean
* git-buildpackage -i -us -uc -b


Upstream update
===============

* debian/rules clean
* git-import-orig path/to/haproxy\_1.6.x.orig.tar.gz
* dch -v '1:1.6.x-1' -M -D unstable 'Upstream release haproxy 1.6.x'
* git add .
* git commit -m 'Upstream release haproxy 1.6.x'
* git tag 1.6.x-1


