FROM rust as builder

ENV SQLX_OFFLINE=true

WORKDIR /aodata-nats
COPY . .
RUN cargo install --path .

FROM ubuntu:latest

ENV ENV=PROD

COPY --from=builder /usr/local/cargo/bin/aodata-nats /usr/local/bin/aodata-nats

CMD ["aodata-nats"]