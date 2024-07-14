Map Format
==========

A map is defined in a JSON file which could look like this:

```
{
    "version": 1,
    "size": 4,
    "betirium": [
        1, 2, 3, 4,
        5, 6, 7, 8,
        7, 6, 6, 5,
        4, 3, 2, 1
    ],
    "terrain": [
        "ssbm",
        "ssmm",
        "ssmm",
        "sssb"
    ]
}
```

`version` is the format version and must be 1.

`size` is the number of cells per map side (maps are always square).

`betirium`: sets Betirium density per cell. The number of items in this array
must be `size * size`. The first item describes the cell with coordinates
`x=0, y=0`, the second one - the cell at `x=1, y=0`, and so on.

`terrain` defines cells' terrain. The number of items in the array must be
`size`. Item at index `i` describes terrain of the cells with `y` coordinate
equal to `i`. Each item is a string of exactly `size` characters, and character
at index `i` describes the cell with `x=i`. Each character may be one of:
 * 'b' - a base;
 * 'm' - mountains terrain;
 * 's' - sand.
