# Kisarra Rules And Documentation

## The Goal

The goal of the game is to ship Betirium. The player who has shipped the most
Betirium by the end of the game wins.

## Map Configuration

The size of the map depends on the number of players:
 * 2 players: 21x21
 * 3 players: 25x25
 * 4 players: 29x29
 * 5 players: 33x33
 * 6 players: 36x36

## Supplies

Each turn, the player receives 2 units of supplies for free, and a certain
amount of supplies for the Beririum sent on the previous turn. For every 2 kg
of beririum sent, the player will receive 1 unit of supplies.

Each unit has a "tank" (capacity) for supplies. Each unit consumes 1 unit of
supplies at the end of each turn.

Supply Trucks can "support" zones. A truck will pick up supplies from the base
and travel to the zone to refill units located there.

When a unit runs out of supplies, its behavior depends on whether it is in a
supported zone. If trucks are assigned to support the zone but none of them
have supplies, the zone is considered unsupported.

If a unit without supplies is inside a supported zone, it will remain there and
be inactive until refilled.

If a unit without supplies is outside the zone, it will travel directly to the
base or to the nearest supported zone to refill.

After refilling (at the base or with the help of a truck), the unit resumes
executing its previous order.

While refilling at the base, if a unit cannot refill to a full tank, it will
not refill at all (waiting for supplies to appear at the base). Harvesters
refill "automatically" when unloading Betirium.
