Map Format
==========

A map is a JSON file. The engine accepts format version 2 only.

```json
{
    "version": 2,
    "size": 4,
    "terrain": [
        "ssbm",
        "ssmm",
        "ssmm",
        "sssb"
    ],
    "betirium_content": [
        1, 2, 3, 4,
        5, 6, 7, 8,
        7, 6, 6, 5,
        4, 3, 2, 1
    ],
    "betirium_regeneration_rate": [
        1, 2, 3, 0,
        5, 6, 7, 0,
        7, 6, 6, 0,
        4, 3, 2, 0
    ]
}
```

`version` is the format version. It must be 2.

`size` is the number of cells per map side. A map is always square.

`terrain` defines the terrain of every cell. The array holds `size` strings.
The string at index `i` describes the cells with `y` equal to `i`. Each string
holds exactly `size` characters, and the character at index `i` describes the
cell with `x` equal to `i`. A character is one of:

 * 'b' - a base;
 * 'm' - mountains terrain;
 * 's' - sand.

`betirium_content` sets the Betirium each cell holds when the game starts. The
array holds `size * size` numbers. The first describes the cell at `x=0, y=0`,
the second the cell at `x=1, y=0`, and so on along each row.

`betirium_regeneration_rate` sets how fast each cell regrows Betirium. It uses
the same length and the same cell order as `betirium_content`. The number is
the amount the cell gains over one full regeneration period, which is 30
turns. The engine spreads that amount evenly over the ticks of the period and
adds it to sand cells only. A cell with 0 never regrows.

The engine ignores any other top-level key, so a generator may record its own
metadata beside these fields.
