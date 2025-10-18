FROM golang:1.23.0-alpine

WORKDIR /app

RUN go install github.com/air-verse/air@latest
RUN go install github.com/go-delve/delve/cmd/dlv@latest

COPY go.mod go.sum ./
RUN go mod download

EXPOSE 8080
CMD ["air", "-c", ".air.toml"]