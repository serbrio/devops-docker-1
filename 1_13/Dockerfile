FROM golang:1.16

WORKDIR = /usr/src/app

ENV PORT=8080

EXPOSE $PORT

COPY go.mod go.sum ./
RUN go mod download

RUN go version

COPY . .

RUN go build -v

ENTRYPOINT ["./server"]
