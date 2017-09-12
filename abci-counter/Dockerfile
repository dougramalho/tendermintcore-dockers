FROM node:alpine

LABEL maintainer="Adriano Ribeiro <adribeiro@gmail.com>"
LABEL description="base image for tendermint ABCI applications."

RUN mkdir /abci
ADD https://github.com/drr00t/js-abci/archive/master.zip /abci
# VOLUME  /root/.tendermint

RUN unzip /abci/master.zip
RUN cd /js-abci-master
RUN npm install /js-abci-master/.

EXPOSE 46658/tcp

ENTRYPOINT ["node"]
CMD ["/js-abci-master/example/app.js"]