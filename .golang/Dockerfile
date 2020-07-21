# 2.07 MB
FROM golang:alpine AS builder

WORKDIR /app

COPY main.go .
RUN go build  -ldflags '-w -s' -a -installsuffix cgo -o /go/main .
# RUN go build -o /go/main

FROM scratch

COPY --from=builder /go/main /go/main

CMD ["/go/main"]