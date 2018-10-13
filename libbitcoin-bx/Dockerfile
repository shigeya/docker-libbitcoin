From ubuntu:bionic as build

RUN apt-get update && apt-get -y install wget && \
    cd /usr/local/bin && \
	 wget https://github.com/libbitcoin/libbitcoin-explorer/releases/download/v3.2.0/bx-linux-x64-qrcode  && \
	chmod a+rx bx-linux-x64-qrcode && \
	ln -s bx-linux-x64-qrcode bx

From ubuntu:bionic
COPY --from=build /usr/local/bin/bx-linux-x64-qrcode /usr/local/bin
RUN ln -s /usr/local/bin/bx-linux-x64-qrcode /usr/local/bin/bx

ENTRYPOINT ["bx"]
