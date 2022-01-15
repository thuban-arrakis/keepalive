FROM golang

ENV CGO_ENABLED=0 
ENV GOOS=linux 
ENV GO111MODULE=auto

COPY . /go/src/api
WORKDIR /go/src/api
RUN go get -d -v ./...
RUN go install -v ./...
ENTRYPOINT env GODEBUG=http2debug=2 go run main.go
EXPOSE 50051
