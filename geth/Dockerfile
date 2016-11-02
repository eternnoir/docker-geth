FROM alpine:latest

ENV GETH_VERSION 1.4.18

RUN apk add --update go alpine-sdk && \
	git clone --branch v$GETH_VERSION https://github.com/ethereum/go-ethereum.git --depth 1 && \
	cd go-ethereum && make geth && mv build/bin/geth /bin && \
	apk del go alpine-sdk && rm -rf /var/cache/apk/* && cd .. && rm -rf go-ethereum

