# opening_hours_map

[opening_hours](http://wiki.openstreetmap.org/wiki/Key:opening_hours) tag is used in [OpenStreetMap](http://openstreetmap.org) project to describe time ranges when a specific facility (for example, a cafe) is open.

This map shows the opening_hours as nicely readable time table.

[Check it out][online]

[online]: http://openingh.openstreetmap.de

## Install

Just clone the repository:

```
git clone --recursive https://github.com/ypid/opening_hours_map.git
```

and install it’s dependencies (execute inside the repository):
```
make installDependencies
```

# Dependencies
* This map uses the [opening_hours.js][oh-lib] library.

[oh-lib]: https://github.com/ypid/opening_hours.js

# Author
[Robin `ypid` Schneider](http://wiki.openstreetmap.org/wiki/User:Ypid)

# Credits
Big thanks goes to Netzwolf how created some OpenLayers extensions and [examples][]. He also created the same map showing opening\_hours with his JS implementation (which is withdrawn in favour of opening\_hours.js). Big parts of his code are still in use for the map. Although most code around the opening\_hours interpretation was rewritten.

[examples]: http://www.netzwolf.info/kartografie/openlayers/
