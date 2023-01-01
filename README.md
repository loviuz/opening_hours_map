# opening_hours_map

[![Build Status](https://travis-ci.org/opening-hours/opening_hours_map.svg?branch=master)](https://travis-ci.org/opening-hours/opening_hours_map)

[opening_hours](https://wiki.openstreetmap.org/wiki/Key:opening_hours) tag is used in [OpenStreetMap](https://openstreetmap.org) project to describe time ranges when a specific facility (for example, a cafe) is open.

This map shows the opening_hours as nicely readable time table.

[Check it out][online]

A mirror is setup up under: https://openingh.ypid.de/

## Install

Just clone the repository:

```Shell
git clone --recursive https://github.com/opening-hours/opening_hours_map.git
```

and install it’s dependencies (execute inside the repository):

```Shell
sudo apt-get install jq
npm install bower -g
npm install uglify-js -g
make dependencies-get
cd opening_hours.js && npm i && cd ..
```

## How does it work?

The map uses OpenLayers to show a base map from OpenStreetMap. An additional optional layer shows POIs which are tagged with opening_hours. The data for this additional layer is queried for from the [OverpassAPI][]. The basic query in [OverpassQL][] looks like this:

    [out:json][timeout:3][bbox:{{bbox}}];
    (
        node["opening_hours"];
        way["opening_hours"];
    );
    out body center 1000;

## Dependencies

* This map is build with [OpenLayers][ol-lib].
* The opening_hours evaluation is handled by the [opening_hours.js][oh-lib] library.

## Author
[Robin `ypid` Schneider](https://wiki.openstreetmap.org/wiki/User:Ypid)

<!-- Credits {{{ -->
## Credits ##
* Big thanks goes to Netzwolf how created some OpenLayers extensions and [examples][]. He also created the same map showing opening\_hours with his JS implementation (which is withdrawn in favour of opening\_hours.js). Big parts of his code are still in use for the map. Although most code around the opening\_hours interpretation was rewritten.

* Also thanks to FOSSGIS for hosting a public instance of this service. See the [wiki][fossgis-project].

<!-- }}} -->

[ol-lib]: http://openlayers.org/
[oh-lib]: https://github.com/opening-hours/opening_hours.js
[examples]: http://www.netzwolf.info/kartografie/openlayers/
[OverpassAPI]: https://overpass-api.de/
[OverpassQL]: https://wiki.openstreetmap.org/wiki/OverpassQL
[online]: http://openingh.openstreetmap.de
[fossgis-project]: https://wiki.openstreetmap.org/wiki/FOSSGIS/Server/Projects/opening_hours.js
