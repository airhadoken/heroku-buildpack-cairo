FROM mojodna/cedar-14-stack

ENV DEBIAN_FRONTEND noninteractive

RUN \
  apt-get upgrade -y

ADD ./pixman.tar.gz /tmp
RUN \
  cd /tmp/pixman-* && \
  ./configure --prefix=/app/vendor/pixman && \
  make install && \
  cd /app/vendor/pixman && \
  tar zcf /tmp/pixman-cedar-14.tar.gz .

ADD ./freetype.tar.bz2 /tmp
RUN \
  cd /tmp/freetype-* && \
  ./configure --prefix=/app/vendor/freetype && \
  make && \
  make install && \
  cd /app/vendor/freetype && \
  tar zcf /tmp/freetype-cedar-14.tar.gz .

ADD ./giflib.tar.bz2 /tmp
RUN \
  cd /tmp/giflib-* && \
  ./configure --prefix=/app/vendor/giflib && \
  make install-exec install-data && \
  cd /app/vendor/giflib && \
  tar zcf /tmp/giflib-cedar-14.tar.gz .

ADD ./fontconfig.tar.bz2 /tmp
RUN \
  cd /tmp/fontconfig-* && \
  ./configure --prefix=/app/vendor/fontconfig && \
  make install && \
  cd /app/vendor/fontconfig && \
  tar zcf /tmp/fontconfig-cedar-14.tar.gz .

ENV PKG_CONFIG_PATH /app/vendor/pixman/lib/pkgconfig:/app/vendor/freetype/lib/pkgconfig:/app/vendor/fontconfig/lib/pkgconfig

ADD ./cairo.tar.xz /tmp
RUN \
  cd /tmp/cairo-* && \
  ./configure --prefix=/app/vendor/cairo && \
  make install && \
  cd /app/vendor/cairo && \
  tar zcf /tmp/cairo-cedar-14.tar.gz .

ENV PKG_CONFIG_PATH /app/vendor/pixman/lib/pkgconfig:/app/vendor/freetype/lib/pkgconfig:/app/vendor/fontconfig/lib/pkgconfig:/app/vendor/cairo/lib/pkgconfig

ADD ./harfbuzz.tar.bz2 /tmp
RUN \
  cd /tmp/harfbuzz-* && \
  ./configure --prefix=/app/vendor/harfbuzz && \
  make install && \
  cd /app/vendor/harfbuzz && \
  tar zcf /tmp/harfbuzz-cedar-14.tar.gz .

ADD ./pango.tar.xz /tmp
RUN \
  cd /tmp/pango-* && \
  ./configure --prefix=/app/vendor/pango && \
  make install && \
  cd /app/vendor/pango && \
  tar zcf /tmp/pango-cedar-14.tar.gz .
