Map Format
==========

A map is defined in a JSON file which could look like this:

```
{
    "size": 4,
    "playersQuantity": 2,
    "betirium": [
        1, 2, 3, 4,
        5, 6, 7, 8,
        7, 6, 6, 5,
        4, 3, 2, 1
    ],
    "basePositions": [{"x": 2, "y": 0}, {"x": 3, "y": 3}]
}
```

`size` is the number of cells per map side (maps are always square).

`playersQuantity` defines the number of players the map is for.

`betirium`: sets Betirium density per cell. The number of items in this array
must be `size * size`. The first item describes the cell with coordinates
`x=0, y=0`, the second one - the cell at `x=1, y=0`, and so on.

`basePositions` is an array of length `playersQuantity` which defines where
players' bases are.
