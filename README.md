# stockfih

`stockfih` is a small modified Stockfish build for Windows.

It is based on the official Stockfish dev build/source from:

```text
Stockfish dev-20260426-1a882efc
```

This project is not a new chess engine from scratch. It is a modified Stockfish source tree with machine-specific stronger default UCI settings.

## Changes

- Default `Threads` changed to `8`
- Default `Hash` changed to `8192` MB
- Default `Ponder` changed to `true`
- Default `UCI_Elo` changed to the maximum value, `3190`
- Default `SyzygyPath` set to:

```text
Z:\syzygy\3-4-5-wdl;Z:\syzygy\6-wdl;Z:\syzygy\3-4-5-dtz;Z:\syzygy\6-dtz
```

- Windows startup attempts to set the engine process to high priority

## Important Performance Note

The locally compiled `stockfih.exe` works, but benchmark testing on the original machine showed it was slower than the official optimized Stockfish dev AVX-512ICL binary.

Use this project as a source-modified Stockfish experiment, not as a claim that it is stronger than official Stockfish.

## Build Notes

The Windows binary was compiled with a portable MinGW/GCC toolchain.

The official Stockfish build system may download required NNUE network files during build. The large `.nnue` files and compiled `.exe` files are intentionally not stored in this repository.

## License

This project is based on Stockfish and is licensed under the GNU General Public License v3.0 or later.

See `Copying.txt`.

