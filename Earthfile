FROM ekidd/rust-musl-builder:stable
WORKDIR /work

build:
    COPY . ./
    RUN cargo build --release
    SAVE ARTIFACT target /target AS LOCAL target

docker:
    FROM scratch
    COPY +build/target/x86_64-unknown-linux-musl/release/rust-single-binary /app/
    ENTRYPOINT ["/app/rust-single-binary"]
    SAVE IMAGE rust-single-binary
