FROM debian:10 AS builder

RUN apt-get update \
    && apt-get install -y git-core build-essential

RUN git clone https://www-dev.cockos.com/ninjam/ninjam.git \
    && cd ninjam/ninjam/server \
    && make


FROM debian:10
RUN mkdir -p /ninjam
WORKDIR /ninjam
COPY --from=builder /ninjam/ninjam/server/ninjamsrv /usr/bin/ninjamsrv
