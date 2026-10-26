FROM ubuntu:24.04

WORKDIR = /usr/src/app

ENV PORT=8080

EXPOSE $PORT

RUN apt-get update

RUN apt-get install -y curl

RUN curl -sL https://go.dev/dl/go1.16.linux-amd64.tar.gz -o go1.16.linux-amd64.tar.gz

RUN rm -rf /usr/local/go && tar -C /usr/local -xzf go1.16.linux-amd64.tar.gz

ENV PATH="$PATH:/usr/local/go/bin"

ENV PATH="$PATH:$(go env GOPATH)/bin"

RUN echo $PATH

RUN bash -c "source ${HOME}/.bashrc" 

RUN echo $PATH

RUN go version

COPY . .

RUN go build

ENTRYPOINT ["./server"]
