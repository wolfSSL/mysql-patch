# mysql-patch
patch for mysql with updated wolfSSL

To run patch copy mysql-5.6.22-wolfssl.patch into the same directory with current MYSQL source code. (On mac this is something like /usr/local/src/)
From the terminal in the same direcotry containing the patch and current MYSQL source code run ""patch -s -p0 < mysql-5.6.22-wolfssl.patch""
To build using updated SSL make MYSQL with the command ""cmake . -DWITH_SSL=bundled"" (from inside the MYSQL source code directory)
Then run the standard make -- make install
