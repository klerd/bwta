Class header file: [BWTA/Polygon.h](http://code.google.com/p/bwta/source/browse/trunk/include/BWTA/Polygon.h#)

A BWTA::[Polygon](Polygon.md) is a std::vector of BWAPI::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) objects, so to iterate over the vertices of a BWTA::[Polygon](Polygon.md) you just need to iterate over the vector.

Methods:

  * [getArea](#getArea.md)
  * [getPerimeter](#getPerimeter.md)
  * [getCenter](#getCenter.md)
  * [getNearestPoint](#getNearestPoint.md)
  * [isInside](#isInside.md)

### getArea ###
double getArea() const;

Returns the area of the polygon.

### getPerimeter ###
double getPerimeter() const;

Returns the perimeter of the polygon.

### getCenter ###
[BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) getCenter() const;

Returns the centroid of the polygon.

### getNearestPoint ###
BWAPI::Position getNearestPoint(BWAPI::Position p) const;

Returns the point on the boundary of the polygon that is nearest to the given point.

### isInside ###
bool isInside([BWAPI](http://code.google.com/p/bwapi/wiki/BWAPIManual)::[Position](http://code.google.com/p/bwapi/wiki/Misc#Position) p) const;

Returns true if the given point is inside the polygon.