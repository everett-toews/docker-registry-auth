FROM golang:1.8-alpine as build

RUN apk --no-cache add git
RUN go get -v -u -f github.com/tools/godep github.com/jteeuwen/go-bindata/...

COPY . /go/src/github.com/cesanta/docker_auth/auth_server
WORKDIR /go/src/github.com/cesanta/docker_auth/auth_server

RUN go get -v -d .
RUN go install -v .


FROM alpine:latest

RUN apk --no-cache add curl jq

COPY --from=build /go/bin/auth_server .

EXPOSE 5001

ENTRYPOINT ["./auth_server"]
CMD ["/config/auth_config.yml"]
