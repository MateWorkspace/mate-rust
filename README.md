# mate-rust

Shared Rust libraries for Mate services. Each library lives under `crates/` and has
its own public API, tests, and documentation.

## Libraries

- **mate-pgdt**: context-aware PostgreSQL execution and transaction orchestration
  using native SQLx types. See [the crate documentation](crates/mate-pgdt/README.md).

## Development

Rust 1.94 or newer is required.

```sh
cargo check --workspace
cargo test --workspace
cargo clippy --workspace --all-targets --all-features -- -D warnings
cargo fmt --all -- --check
```

PostgreSQL integration tests require an isolated database and are ignored by
default. Run them explicitly using `MATE_PGDT_TEST_DATABASE_URL`; details are in
the crate README. Keep the workspace lockfile in version control for reproducible development.

Services can depend on a local checkout with a Cargo path dependency, or use a Git
dependency pinned to a release tag or revision once the repository is hosted.
