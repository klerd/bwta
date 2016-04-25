Class header file: [BWTA/BaseLocation.h](http://code.google.com/p/bwta/source/browse/trunk/include/BWTA/BaseLocation.h#)

A BaseLocation a position on the map where it makes sense to place a base (i.e. near minerals).

Methods:

  * [getPosition](#getPosition.md)
  * [getTilePosition](#getTilePosition.md)
  * [getRegion](#getRegion.md)
  * [minerals](#minerals.md)
  * [gas](#gas.md)
  * [getMinerals](#getMinerals.md)
  * [getStaticMinerals](#getStaticMinerals.md)
  * [getGeysers](#getGeysers.md)
  * [getGroundDistance](#getGroundDistance.md)
  * [getAirDistance](#getAirDistance.md)
  * [isIsland](#isIsland.md)
  * [isMineralOnly](#isMineralOnly.md)
  * [isStartLocation](#isStartLocation.md)

### getPosition ###
[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) getPosition() const;

Returns the position of the center of the base location.

### getTilePosition ###
[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) getTilePosition() const;

Returns the tile position of the base location.

### getRegion ###
[Region](Region.md)`*` getRegion() const;

Returns the region the base location is in.

### minerals ###
int minerals() const;

Returns the total mineral resource count of all accessible mineral patches.

### gas ###
int gas() const;

Returns the total gas resource count of all accessible vespene geysers.

### getMinerals ###
const std::set<[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Unit](http://code.google.com/p/bwapi/wiki/Unit)`*`> &getMinerals();

Returns the set of accessible mineral patches near the base location.

### getStaticMinerals ###
const std::set<[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Unit](http://code.google.com/p/bwapi/wiki/Unit)`*`> &getStaticMinerals() const;

Returns the set of all mineral patches near the base location, including mined out and invisible ones.

### getGeysers ###
const std::set<[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Unit](http://code.google.com/p/bwapi/wiki/Unit)`*`> &getGeysers() const;

Returns the set of vespene geysers near the base location. If the set is empty, the base location is mineral only.

### getGroundDistance ###
double getGroundDistance(BaseLocation`*` other) const;

Returns the ground (walking) distance to the given base location. If its impossible to reach the given base location from the current one, this will return a negative value.

### getAirDistance ###
double getAirDistance(BaseLocation`*` other) const;

Returns the air (flying) distance to the given base location.

### isIsland ###
bool isIsland() const;

Returns true if the base location not in not reachable by ground from any other base location.

### isMineralOnly ###
bool isMineralOnly() const;

Returns true if the base location is mineral-only.

### isStartLocation ###
bool isStartLocation() const;

Returns true if the base location is a start location.