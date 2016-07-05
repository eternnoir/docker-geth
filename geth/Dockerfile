FROM ubuntu:xenial
MAINTAINER Frank Wang "eternnoir@gmail.com"

ENV GETH_VERSION 1.4.9

RUN apt-get update && apt-get install -y git build-essential libgmp3-dev golang && \
	git clone --branch v$GETH_VERSION https://github.com/ethereum/go-ethereum.git --depth 1 && \
	cd go-ethereum && make geth && mv build/bin/geth /bin && \
	apt-get purge -y git build-essential libgmp3-dev golang && apt-get autoremove -y && \
	cd ~/ && rm -rf go-ethereum

ENTRYPOINT ["/bin/geth"]


