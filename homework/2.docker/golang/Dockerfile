FROM golang:alpine3.16 AS builder

RUN mkdir /app

COPY . /app

WORKDIR /app
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o server .


FROM alpine

COPY --from=builder /app/server /

EXPOSE 8080
CMD ["/server"]
