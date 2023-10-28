FROM golang:1.21-alpine as Builder

WORKDIR /usr/src/app
COPY main.go /usr/src/app

RUN go build main.go

CMD ["./main"]

FROM scratch
WORKDIR /usr/src/app
COPY --from=Builder /usr/src/app/main .
CMD ["./main"]