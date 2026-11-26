# World News — Wednesday 26 November 2026

[![make.fun · news-image-20261126](https://make.fun/badge/news-image-20261126.svg)](https://make.fun/bounty/news-image-20261126?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261126)
[![rank](https://make.fun/badge/news-image-20261126/danielhutapea36/news-image-20261126-entry/rank.svg)](https://make.fun/bounty/news-image-20261126/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261126)
[![reward](https://make.fun/badge/news-image-20261126/danielhutapea36/news-image-20261126-entry/reward.svg)](https://make.fun/bounty/news-image-20261126?utm_source=github&utm_medium=readme&utm_campaign=news-image-20261126)

An entry for the [news-image-20261126](https://make.fun/bounty/news-image-20261126) bounty on make.fun: a single 1024×1024 news image summarising the day's world headlines, built to be read at a glance.

## The six stories

1. **US proposes new tariffs on 14 trading partners** — Reuters / BBC
2. **Judges urge dropping top Netanyahu charges** — BBC
3. **Colombia frees all 76 hostages in supermarket siege** — BBC / Reuters
4. **Israeli strike kills senior Hamas official in Gaza** — BBC
5. **US stocks fall further as AI fears deepen** — BBC / Reuters
6. **Also today:** Ukraine says five Russian jets hit in airfield strike; six dead in a plane crash off the Mississippi coast; North Korea expels a Swiss diplomat; Sudan drone strikes kill 19 civilians — BBC / Reuters

## The image

- File: `entry.png`
- Dimensions: 1024×1024
- Size: 139155 bytes
- SHA-256: `ab0dd7554a7b02a2de2954a41e5dc2ec6d5e72a658076a6f3faa118dc5bc6cf4`

## How it works

The PNG was drawn during the build (Pillow, offline) and committed to this repository. The entry program itself (`main.py`) is standard-library-only: it simply copies the committed `entry.png` to the output directory — the pattern the competition's own starter uses ("the simplest program copies an image the repository holds").

This matters because the grader runs the program in an environment where "standard library only: nothing is installed before it runs". A program that imports Pillow would fail there with `ModuleNotFoundError` even though it works locally. This entry program imports only `argparse`, `hashlib`, `os`, `struct`, `sys`, and `pathlib`, makes no network calls, and is fully deterministic: the same committed bytes are copied every run.

Before writing, the program verifies the image: PNG magic bytes, a 13-byte IHDR chunk, 1024×1024 dimensions, and size at most 1 MiB. After copying, it reads the output back and checks the bytes match the committed image exactly.

## Run it

```bash
MAKEFUN_OUTPUT_DIR=/tmp/ni26-out python3 main.py
```

Or check the committed image without writing anything:

```bash
python3 main.py --verify-only
```

`--out-dir` overrides `$MAKEFUN_OUTPUT_DIR`; if neither is set, the program writes to `/output`. An explicitly set but empty `$MAKEFUN_OUTPUT_DIR` is an error.

## Verification

A successful run exits 0 and prints the output path, byte count, and digest, for example:

```
wrote /tmp/ni26-out/entry.png: 139155 bytes, sha256=ab0dd7554a7b02a2de2954a41e5dc2ec6d5e72a658076a6f3faa118dc5bc6cf4
```

`--verify-only` exits 0 and prints the same size and digest for the committed image. Re-running into a fresh directory produces byte-identical output.

## About make.fun

Built for the make.fun bounty platform — [make.fun](https://make.fun/?ref=danielhutapea36&utm_source=github&utm_medium=readme&utm_campaign=news-image-20261126).
