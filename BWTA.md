Library header file: [BWTA.h](http://code.google.com/p/bwta/source/browse/trunk/include/BWTA.h#)

Global functions:

  * [readMap](#readMap.md)
  * [analyze](#analyze.md)

  * [getRegions](#getRegions.md)
  * [getChokepoints](#getChokepoints.md)
  * [getBaseLocations](#getBaseLocations.md)
  * [getStartLocations](#getStartLocations.md)
  * [getUnwalkablePolygons](#getUnwalkablePolygons.md)

  * [getStartLocation](#getStartLocation.md)

  * [getRegion](#getRegion.md)
  * [getNearestChokepoint](#getNearestChokepoint.md)
  * [getNearestBaseLocation](#getNearestBaseLocation.md)
  * [getNearestUnwalkablePolygon](#getNearestUnwalkablePolygon.md)
  * [getNearestUnwalkablePosition](#getNearestUnwalkablePosition.md)

  * [isConnected](#isConnected.md)

  * [getGroundDistance](#getGroundDistance.md)
  * [getNearestTilePosition](#getNearestTilePosition.md)
  * [getGroundDistances](#getGroundDistances.md)
  * [getGroundDistanceMap](#getGroundDistanceMap.md)
  * [getShortestPath](#getShortestPath.md)

### readMap ###
void readMap();

Reads the contents of the map in to BWTA. This was added so analyze() can be executed in another thread.

### analyze ###
void analyze();

Before any other global functions can be called, the map must first be analyzed. Analyzing a starcraft map can take a long time, depending on your computer, so BWTA also automatically saves the results to a file when it is done. When you call analyze on the same map, BWTA will see that the results file for that map already exists, and load the results from file, rather than re-analyze the map.

### getRegions ###
std::set<[Region](Region.md)`*`>& getRegions();

Returns the set of regions in the map.

### getChokepoints ###
std::set<[Chokepoint](Chokepoint.md)`*`>& getChokepoints();

Returns the set of chokepoints in the map.

### getBaseLocations ###
std::set<[BaseLocation](BaseLocation.md)`*`>& getBaseLocations();

Returns the set of base locations on the map.

### getStartLocations ###
std::set<[BaseLocation](BaseLocation.md)`*`>& getStartLocations();

Returns the set of base locations that are start locations.

### getUnwalkablePolygons ###
const std::set<Polygon`*`>& getUnwalkablePolygons();

Returns the set of unwalkable polygons.

### getStartLocation ###
[BaseLocation](BaseLocation.md)`*` getStartLocation([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Player](http://code.google.com/p/bwapi/wiki/Player)`*` player);

Given a pointer to a BWAPI::Player object, this function returns a pointer to the player's starting base location.

### getRegion ###
[Region](Region.md)`*` getRegion(int x, int y);

[Region](Region.md)`*` getRegion([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) tileposition);

Returns the region that the tile position is inside. Returns NULL if the tile position is not inside any valid region.

### getNearestChokepoint ###
[Chokepoint](Chokepoint.md)`*` getNearestChokepoint(int x, int y);

[Chokepoint](Chokepoint.md)`*` getNearestChokepoint([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) tileposition);

[Chokepoint](Chokepoint.md)`*` getNearestChokepoint([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) position);

Returns the nearest chokepoint (in ground/walking distance). Returns NULL if no chokepoint is reachable from the given tile position (such as in an island component with no chokepoints). The Position version of this function has walk tile accuracy, while the other two have build tile accuracy.

### getNearestBaseLocation ###
[BaseLocation](BaseLocation.md)`*` getNearestBaseLocation(int x, int y);

[BaseLocation](BaseLocation.md)`*` getNearestBaseLocation([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) tileposition);

[BaseLocation](BaseLocation.md)`*` getNearestBaseLocation([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#Position) position);

Returns the nearest base location(in ground/walking distance). Returns NULL if no base location is reachable from the given tile position. The Position version of this function has walk tile accuracy, while the other two have build tile accuracy.

### getNearestUnwalkablePolygon ###
[Polygon](Polygon.md)`*` getNearestUnwalkablePolygon(int x, int y);

[Polygon](Polygon.md)`*` getNearestUnwalkablePolygon([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) tileposition);

Returns the nearest unwalkable polygon. Note: The border of the map is not considered an unwalkable polygon.

### getNearestUnwalkablePosition ###
BWAPI::Position getNearestUnwalkablePosition([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) position);

Returns the nearest position that is on the boundary of an unwalkable polygon, or border of the map.


### isConnected ###
bool isConnected(int x1, int y1, int x2, int y2);

bool isConnected([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) a, [BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) b);

Returns true if there exists a static path between the two given tile positions.

### getGroundDistance ###
double getGroundDistance([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition), [BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) end);

Returns the ground distance between the two given tile positions.

### getNearestTilePosition ###
std::pair<[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition), double> getNearestTilePosition([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition) start, const std::set<[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[TilePosition](http://code.google.com/p/bwapi/wiki/Misc#TilePosition)>& targets);

Returns the tile position in the given set that is closest to the given tile position, along with the ground distance to that tile position.

### getGroundDistances ###
std::map<BWAPI::TilePosition, double> getGroundDistances(BWAPI::TilePosition start, const std::set<BWAPI::TilePosition>& targets);

Returns the distance to each target tile position.

### getGroundDistanceMap ###
void getGroundDistanceMap(BWAPI::TilePosition start, RectangleArray< double >& distanceMap);

Fills up the given RectangleArray distance map with the distance from the given tile position. Tiles not reachable from the given tile position will be set to -1.

### getShortestPath ###
std::vector<BWAPI::TilePosition> getShortestPath(BWAPI::TilePosition start, BWAPI::TilePosition end);

Returns the shortest path from the start tile position to the end tile position. If no path exists, the vector will be empty.

std::vector<BWAPI::TilePosition> getShortestPath(BWAPI::TilePosition start, const std::set<BWAPI::TilePosition>& targets);

Returns the shortest path from the start tile position to the closest target tile position. If no path exists to any of the target tile positions, the vector will be empty.