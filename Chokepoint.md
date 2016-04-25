Class header file: [BWTA/Chokepoint.h](http://code.google.com/p/bwta/source/browse/trunk/include/BWTA/Chokepoint.h#)

A chokepoint connects exactly two regions.

Methods:

  * [getRegions](#getRegions.md)
  * [getSides](#getSides.md)
  * [getCenter](#getCenter.md)
  * [getWidth](#getWidth.md)

### getRegions ###
const std::pair<[Region](Region.md)`*`,[Region](Region.md)`*`>& getRegions() const;

Returns the two regions the chokepoint connects.

### getSides ###
const std::pair<[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position),[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position)>& getSides() const;

Returns the two sides of the chokepoint.

### getCenter ###
[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) getCenter() const;

Returns the center of the chokepoint.

### getWidth ###
double getWidth() const;

Returns the width of the chokepoint.