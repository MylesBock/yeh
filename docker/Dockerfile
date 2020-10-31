FROM golang:alpine AS build

COPY ./hey /app

WORKDIR /app

RUN go get ./... && \
    CGO_ENABLED=0 GOOS=linux go build -o hey


FROM alpine:latest

COPY --from=build /app/hey /hey
RUN apk add --no-cache bash
CMD ["/hey"]
