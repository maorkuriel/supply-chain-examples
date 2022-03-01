FROM rust:1.55-slim-bullseye@sha256:1ee75015d02a52243217fd9e9e9ca4482ce677dc31e0248d80b4b7ce485a2cbb as builder
WORKDIR /usr/src/demo
COPY . .
RUN cargo build --release

FROM debian:bullseye-slim@sha256:d5cd7e54530a8523168473a2dcc30215f2c863bfa71e09f77f58a085c419155b
WORKDIR /usr/src/demo
COPY --from=builder /usr/src/demo/target/release/ocidemo /usr/local/bin
ENTRYPOINT ["ocidemo"]
