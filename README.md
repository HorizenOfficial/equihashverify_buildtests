Docker images building equihashverify node module and running mocha tests.
```
Platforms:
Alpine Linux, boost 1.62, musl-libc
Ubuntu Bionic, boost 1.65
Debian oldstable, boost 1.55
Debian stable, boost 1.62
Debian testing, boost 1.62
Centos7, boost 1.53
Fedora, boost 1.64
```
To build all images and run the tests:
```
 for folder in *; do [ -d "${folder}" ] && docker build -t equihashverify_$folder ./$folder \
 && docker run equihashverify_$folder || break; done
```
