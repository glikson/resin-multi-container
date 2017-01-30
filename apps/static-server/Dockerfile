FROM resin/qemux86-64-alpine

RUN apk add --update ruby

WORKDIR /downloads
CMD /usr/bin/ruby -run -ehttpd . -p80
