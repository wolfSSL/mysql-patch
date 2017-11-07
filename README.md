# mysql-patch
patch for mysql with updated wolfSSL

MYSQL 8.0.0 can be found at downloads.mysql.com/archives/community/.
Select version "8.0.0" and select platform "source code". This patch was done on the Generic Linux (Architecture Independent), Compressed TAR Archive bundle. mysql-8.0.0.tar.gz

To run the patch, copy wolfssl-mysql-8.0.0.patch into the same directory with current MYSQL source code.
From the terminal in the same direcotry containing current MYSQL source code run
```
    patch -p1 < [directory of]/wolfssl-mysql-8.0.0.patch
```
Replace the mysql-8.0.0/extra/yassl directory with wolfssl and follow steps in wolfssl/IDE/MYSQL direcotry. Next to build using updated SSL make MYSQL with the command
```
cmake . -DBUILD_CONFIG=mysql_release -DWITH_SSL=bundled (from inside the MYSQL source code directory)
```
Then run the standard make && sudo make install

Note: When building on Linux CFLAGS="-g1" may be needed to work around a Binutils bug. To build then it would be the command
```
CFLAGS="-g1" cmake . -DBUILD_CONFIG=mysql_release -DWITH_SSL=bundled
```

###SHA256 sum
$ shasum -a 256 wolfssl-mysql-8.0.0.patch.zip
b1309074f23052e5230920031347804a8065d7537e70a4d67d0daa3f40be1c46

####Product Licensing for wolfSSL

wolfSSL’s software is available under two distinct licensing models: open source and standard commercial licensing.

###Open Source

CyaSSL, yaSSL, wolfCrypt, yaSSH and TaoCrypt software are free software downloads and may be modified to the needs of the user as long as the user adheres to version two of the GPL License. The GPLv2 license can be found on the gnu.org website (http://www.gnu.org/licenses/old-licenses/gpl-2.0.html).

###Commercial Licensing

Businesses and enterprises who wish to incorporate wolfSSL products into proprietary appliances or other commercial software products for re-distribution must license commercial versions. For more information about commercial licensing visit www.wolfssl.com

###Questions?
Contact info@wolfssl.com for questions.

