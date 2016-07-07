FROM alpine:latest

ENV GETH_VERSION 1.4.9

RUN apk add --update bash go alpine-sdk && \
	git clone --branch v$GETH_VERSION https://github.com/ethereum/go-ethereum.git --depth 1 && \
	cd go-ethereum && make geth && mv build/bin/geth /bin && \
	apk del bash go alpine-sdk && cd ~/ && rm -rf go-ethereum

ENTRYPOINT ["/bin/geth"]
