# Saorsa Disk (sdisk)

Cross-platform CLI to analyze disk usage and safely clean up stale files.

## Install

```bash
cargo install sdisk
```

## Usage

```bash
# Overview of disks
sdisk info

# Show largest files under a path
sdisk top -p ~/ -c 20

# Find stale files older than 120 days
sdisk stale -p ~/Projects --stale-days 120

# Clean candidates (prompt)
sdisk clean -p ~/Downloads --stale-days 90 --limit 50

# Clean without prompt (DANGEROUS)
sdisk clean -p ~/Downloads --stale-days 90 --limit 50 --yes

# Dry run
sdisk clean -p ~/Downloads --stale-days 90 --dry-run
```

## Contributing

- macOS, Linux, Windows supported
- Lint and format must pass:

```bash
cargo fmt --all
cargo clippy --all-targets --all-features -- -D warnings
cargo test --all-features
```

## License

MIT OR Apache-2.0