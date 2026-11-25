# DQ4 DS – Immigrant save format

Found by comparing real saves with 0 to 24 immigrants (USA En/Fr/Es), and matching the
`EnvoyData` structure of the DQIV decompilation.

## Save block
- 64 KiB save file. The game block starts with the magic `arte` and is `0x3300` bytes long
  (offset `0x7C00` in the tested saves).
- `+0x0008` checksum (u32 LE) = sum of all bytes of the block, counting this field as 0.
- `+0x1FDC` list of 24 received immigrants, `0xC4` (196) bytes each, compact (no gaps).
  Empty slot = all `0xFF`.
- `+0x323C` your own immigrant (same format).

## Immigrant record (196 bytes, in the save)
| Offset | Size | Field |
|---|---|---|
| 0x00 | 4  | unique ID |
| 0x04 | 26 | name (UTF-8, 0-padded) |
| 0x1E | 26 | sender (hero name) |
| 0x38 | 42 | hometown (e.g. "San Slimeburgo") |
| 0x62 | 92 | message (3 lines × 15 chars, padded with spaces) |
| 0xBE | 1  | type (0–50; 50 is hidden) |
| 0xBF | 1  | gender (0 male, 1 female, 2 "???" monster) |
| 0xC0 | 1  | age (0–7) |
| 0xC1 | 1  | hobby (0–63) |
| 0xC2 | 2  | `FF FF` |

## In RAM (USA)
Own immigrant at main-RAM offset `0x0F0080`, received list at `0x0F0154` (stride `0xD4`, with 32-bit
fields for enable/type/gender/age/hobby). Matches `EnvoyData` / `EnvoyManager` in the
decompilation.

## Notes
- The game rejects an immigrant whose ID is already in the list (it replaces it).
- Values above the ranges above freeze the game.
- Special glyphs (♪, curly quotes) use the game's private codes `E2 93 86`, `E2 93 95`… 
