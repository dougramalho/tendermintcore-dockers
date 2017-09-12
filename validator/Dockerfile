FROM busybox:musl

LABEL maintainer="Adriano Ribeiro <adribeiro@gmail.com>"
LABEL description="base image for tendermint core."

# COPY files/nginx.conf /etc/nginx/nginx.conf
# COPY files/default.conf /etc/nginx/conf.d/default.conf

# https://github.com/tendermint/tendermint/blob/master/CHANGELOG.md#0104-septemeber-5-2017
ENV TENDERMINT_VERSION 0.10.4 

RUN mkdir /tc
ADD https://github.com/tendermint/tendermint/releases/download/v${TENDERMINT_VERSION}/tendermint_${TENDERMINT_VERSION}_linux_amd64.zip /tc
# VOLUME  /root/.tendermint

RUN unzip /tc/tendermint_${TENDERMINT_VERSION}_linux_amd64.zip && \
    rm -rf /tc/tendermint_${TENDERMINT_VERSION}_linux_amd64.zip

# VOLUME ["/root/.tendermint/"]

RUN ./tendermint init

EXPOSE 46657/tcp

ENTRYPOINT ["./tendermint"]
CMD ["node"] 

