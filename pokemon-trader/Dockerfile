FROM docker.io/library/golang:1.21-alpine AS build
WORKDIR /app
COPY go.mod .
COPY main.go .
RUN go build -o pokemon-trader .

FROM docker.io/library/alpine:3.19
WORKDIR /app
COPY --from=build /app/pokemon-trader .
COPY static/ static/
EXPOSE 3000
CMD ["./pokemon-trader"]
