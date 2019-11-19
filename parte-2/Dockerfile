FROM golang:1.8 as builder
WORKDIR /opt/app
COPY codeeducation.go .

RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main .

FROM scratch
WORKDIR /opt/app
COPY --from=builder /opt/app .
CMD ["./main"]
