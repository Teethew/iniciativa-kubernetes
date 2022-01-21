FROM golang:1.7.3 as build
WORKDIR /app
COPY . .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main
CMD [ "./main" ]

FROM alpine:3.14
WORKDIR /app
COPY --from=build /app/main .
CMD [ "./main" ]