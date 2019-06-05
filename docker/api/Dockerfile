FROM golang:1.12.5-alpine3.9

COPY Gopkg.toml /go/src/api/
COPY main.go /go/src/api/

WORKDIR /go/src/api/

RUN apk update \
  && apk add --no-cache git \
  && go get -u github.com/codegangsta/gin \
  && go get -u github.com/gin-gonic/gin \ 
  && go get -u github.com/golang/dep/cmd/dep \
  && dep ensure

CMD gin -i run