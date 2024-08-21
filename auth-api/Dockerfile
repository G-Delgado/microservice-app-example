FROM golang:1.18.2-alpine

WORKDIR /app

COPY . .

RUN go mod tidy
RUN go build -o auth-api

EXPOSE 8000

CMD ["./auth-api"]
