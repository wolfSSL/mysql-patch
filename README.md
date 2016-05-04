# mysql-patch
patch for mysql with updated wolfSSL

To run patch copy mysql-5.6.22-wolfssl.patch into the same directory with current MYSQL source code. (On mac this is something like /usr/local/src/)
From the terminal in the same direcotry containing current MYSQL source code run
```
    patch -s -p1 < <directory of>/mysql-5.6.22-wolfssl.patch
```
To build using updated SSL make MYSQL with the command
```
cmake . -DWITH_SSL=bundled (from inside the MYSQL source code directory)
```
Then run the standard make -- make install

###SHA256 sum
$ shasum -a 256 wolfssl-mysql-5.6.30.patch.zip
7df65d141a645c46f7db9de74d5e111657819c6d411562f0afbdf3a293c678a9

####Product Licensing for wolfSSL

wolfSSL’s software is available under two distinct licensing models: open source and standard commercial licensing.

###Open Source

CyaSSL, yaSSL, wolfCrypt, yaSSH and TaoCrypt software are free software downloads and may be modified to the needs of the user as long as the user adheres to version two of the GPL License. The GPLv2 license can be found on the gnu.org website (http://www.gnu.org/licenses/old-licenses/gpl-2.0.html).

###Commercial Licensing

Businesses and enterprises who wish to incorporate wolfSSL products into proprietary appliances or other commercial software products for re-distribution must license commercial versions. For more information about commercial licensing visit www.wolfssl.com
