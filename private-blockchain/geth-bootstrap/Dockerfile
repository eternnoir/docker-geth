FROM eternnoir/geth:latest
MAINTAINER Frank Wang "eternnoir@gmail.com"

RUN mkdir /gethdata
RUN mkdir /gtmp

ADD Gensis.json /gtmp/

RUN /bin/geth --datadir /gethdata init /gtmp/Gensis.json

VOLUME ["/gethdata"]

RUN rm -rf /gtmp

EXPOSE 8545
EXPOSE 30303

ENTRYPOINT ["/bin/geth", "--datadir", "/gethdata", "--networkid", "55566"]

