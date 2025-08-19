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

# Show largest files under a path (interactive by default)
sdisk top -p ~/ -c 20

# Find stale files older than 120 days (interactive)
sdisk stale -p ~/Projects --stale-days 120

# Clean candidates (interactive)
sdisk clean -p ~/Downloads --stale-days 90 --limit 50

# Non-interactive modes
#   --non-interactive: no selection UI
#   --yes: skip confirmation in non-interactive mode
#   --dry-run: preview deletions

# Example: non-interactive, auto-confirm
sdisk clean -p ~/Downloads --stale-days 90 --limit 50 --non-interactive --yes

# Example: dry run
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