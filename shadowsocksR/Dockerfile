#
# Dockerfile for ShadowsocksR
#

FROM alpine:3.7

ENV SSR_URL https://github.com/shadowsocksr-backup/shadowsocksr/archive/manyuser.zip

RUN set -ex \
    && apk --update add --no-cache libsodium py-pip \
    && pip --no-cache-dir install $SSR_URL \
    && rm -rf /var/cache/apk

ENV SERVER_ADDR 	0.0.0.0
ENV SERVER_PORT 	19891
ENV PASSWORD    	passgfw
ENV METHOD      	aes-128-ctr
ENV PROTOCOL    	auth_aes128_md5
ENV OBFS        	tls1.2_ticket_auth_compatible
ENV TIMEOUT     	300
ENV PROTOCOLPARAM   32

WORKDIR /usr/bin/

CMD ssserver -s $SERVER_ADDR \
             -p $SERVER_PORT \
             -k $PASSWORD    \
             -m $METHOD      \
             -O $PROTOCOL    \
             -o $OBFS        \
             -t $TIMEOUT     \
             -G $PROTOCOLPARAM