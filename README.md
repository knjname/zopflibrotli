
# zopflibrotli Docker image - zopfli & brotli CLIs on busybox

[![](https://images.microbadger.com/badges/image/knjname/zopflibrotli.svg)](https://microbadger.com/images/knjname/zopflibrotli "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/knjname/zopflibrotli.svg)](https://microbadger.com/images/knjname/zopflibrotli "Get your own version badge on microbadger.com")

A docker image for using [zopfli](https://github.com/google/zopfli.git) and [brotli](https://github.com/google/brotli.git) simultaneously.

I am to use this image for compressing files to be delivered by Nginx.

```Dockerfile
FROM knjname/zopflibrotli:latest as compressor
RUN find /var/www/html -type f | xargs brotli
RUN find /var/www/html -type f | grep -v '\.br$' | xargs zopfli
```

## Build

```
$ docker build -t knjname/zopflibrotli:latest .
```

## License

The files in this repository are licensed by MIT License.
