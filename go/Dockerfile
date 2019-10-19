FROM golang:<<GO_VERSION>> AS build

WORKDIR /go/src/app
COPY . /go/src/app
RUN go get -d -v ./...
RUN go build -o /go/bin/app cmd/<<PROJECT>>/main.go

FROM gcr.io/distroless/base
COPY --from=build /go/bin/app /
CMD ["/app"]
