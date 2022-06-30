FROM golang:alpine as builder

WORKDIR /go/src/app

RUN go mod init app/codeeducation
COPY *.go ./

RUN go mod download

RUN go build -o ./codeeducation

CMD [ "./codeeducation" ]

FROM hello-world

COPY --from=builder /go/src/app/codeeducation /hello
