<p align="center">
  <img src="logo_256.png" alt="Pattern Select logo" width="160">
</p>

<h1 align="center">Pattern Select for Maya</h1>

<p align="center">
  Select faces, edges or vertices by a repeating pattern - "select 1, skip 2" along any strip, ring or loop.
</p>

---

## Features

- Works with **faces, edges (rings and loops) and vertices**
- Simple **Select / Skip** counts - no pattern strings needed
- Optional **custom pattern** for irregular selections (`1 1 0 1 0 0`)
- Follows the strip around **bends and corners** (order is detected from mesh topology)
- Handles strips that are **several faces wide** (e.g. a wide row next to a thin row)
- Handles **multiple strips** at once, with the pattern restarting on each strip
- **Start offset** and **Invert** options
- Single MEL file, no dependencies

## Installation

**Quick run**

1. Open the Script Editor and switch to a **MEL** tab.
2. Paste the contents of `patternSelect.mel` and run it.

**Permanent**

1. Copy `patternSelect.mel` into your Maya scripts folder (e.g. `Documents/maya/scripts`).
2. Run this in a MEL tab whenever you need it (or drag it onto a shelf):

```mel
source "patternSelect.mel"; patternSelect;
```

## Usage

1. Select a strip / ring / loop of faces, edges or vertices.
2. Set **Select (count)** and **Skip (count)**.
3. Press **Select**.

| Select | Skip | Result                 |
|:------:|:----:|------------------------|
| 1      | 1    | every other component  |
| 1      | 2    | every third component  |
| 2      | 1    | two selected, one skipped |

### Options

| Option                         | Description                                                                 |
|--------------------------------|-----------------------------------------------------------------------------|
| Start offset                   | Shifts where the pattern starts                                             |
| Use custom pattern             | Type your own pattern, `1` = select, `0` = skip                             |
| Order                          | Strip order (auto, topology based), selection order, or component index     |
| Edge type                      | Auto, Ring (rungs across a strip) or Loop (edges end to end)                |
| Restart pattern on each strip  | Restarts the pattern for every separate strip                               |
| Invert                         | Swaps selected and skipped components                                       |

## Notes

- Works on one polygon mesh at a time.
- Face strips are detected most reliably when they are at least ~6 rows long.
- If *Edge type: Auto* picks the wrong mode on a very short selection, choose Ring or Loop manually.

## License

MIT - see the license text at the bottom of `patternSelect.mel`.
