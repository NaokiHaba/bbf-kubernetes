FROM golang:1.21 AS builder
WORKDIR /app
COPY . .
# CGO : c と Go の間のインターフェースを提供するツール
# バイナリサイズを小さくするために CGO_ENABLED=0 を指定
ENV CGO_ENABLED=0
RUN go build -o hello .

FROM scratch
COPY --from=builder /app/hello /hello
CMD ["/hello"]