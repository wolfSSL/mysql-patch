# Updated version of the patch comming shortly

# mysql-patch
patch for mysql with updated wolfSSL

MYSQL 5.6.30 can be found at downloads.mysql.com/archives/community/.
Select version "5.6.30" and select platform "source code". This patch was done on the Generic Linux (Architecture Independent), Compressed TAR Archive bundle. mysql-5.6.30.tar.gz

To run the patch, copy wolfssl-mysql-5.6.30.patch into the same directory with current MYSQL source code.
From the terminal in the same direcotry containing current MYSQL source code run
```
    patch -p1 < [directory of]/wolfssl-mysql-5.6.30.patch
```
To build using updated SSL make MYSQL with the command
```
cmake . -DBUILD_CONFIG=mysql_release -DWITH_SSL=bundled (from inside the MYSQL source code directory)
```
Then run the standard make && sudo make install

Note: When building on Linux CFLAGS="-g1" may be needed to work around a Binutils bug. To build then it would be the command
```
CFLAGS="-g1" cmake . -DBUILD_CONFIG=mysql_release -DWITH_SSL=bundled
```

###SHA256 sum
$ shasum -a 256 wolfssl-mysql-5.6.30.patch.zip
0fb2a0e53e8741b05ace851e6eab814fa90016e96fc2f4f9dc00e70c992079b4

####Product Licensing for wolfSSL

wolfSSL’s software is available under two distinct licensing models: open source and standard commercial licensing.

###Open Source

CyaSSL, yaSSL, wolfCrypt, yaSSH and TaoCrypt software are free software downloads and may be modified to the needs of the user as long as the user adheres to version two of the GPL License. The GPLv2 license can be found on the gnu.org website (http://www.gnu.org/licenses/old-licenses/gpl-2.0.html).

###Commercial Licensing

Businesses and enterprises who wish to incorporate wolfSSL products into proprietary appliances or other commercial software products for re-distribution must license commercial versions. For more information about commercial licensing visit www.wolfssl.com
