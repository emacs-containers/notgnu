FROM debian:buster-slim
RUN apt-get update && apt-get -y --no-install-recommends install \
      libncurses5 \
 && rm -rf /var/lib/apt/lists/*
WORKDIR /build
COPY checksum checksum
ADD https://mistl.org/notgnu/dist/notgnu-2.01n6-1_amd64.deb notgnu.deb
RUN sha256sum notgnu.deb && sha256sum -c checksum
RUN dpkg -i notgnu.deb
WORKDIR /root
CMD ["not"]
