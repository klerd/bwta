Class header file: [BWTA/Region.h](http://code.google.com/p/bwta/source/browse/trunk/include/BWTA/Region.h#)

A region is a partition of the map with a polygon boundary, and is connected to other regions via [chokepoints](Chokepoint.md).

Methods:

  * [getPolygon](#getPolygon.md)
  * [getCenter](#getCenter.md)
  * [getChokepoints](#getChokepoints.md)
  * [getBaseLocations](#getBaseLocations.md)
  * [isReachable](#isReachable.md)
  * [getReachableRegions](#getReachableRegions.md)


### getPolygon ###
const [Polygon](Polygon.md)& getPolygon() const;

Returns the polygon border of the region.

### getCenter ###
const [BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position)& getCenter() const;

Returns the center of the region.

### getChokepoints ###
const std::set<[Chokepoint](Chokepoint.md)`*`>& getChokepoints() const;

Returns the set of chokepoints adjacent to the region.

### getBaseLocations ###
const std::set<[BaseLocation](BaseLocation.md)`*`>& getBaseLocations() const;

Returns the set of base locations in the region.

### isReachable ###
bool isReachable([Region](Region.md)`*` region) const;

Returns true if its possible to walk from this region to the given region.

### getReachableRegions ###
const std::set<[Region](Region.md)`*`>& getReachableRegions() const;

Returns the set of regions reachable from this region.