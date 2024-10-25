# MBTA TILESERVER

Runs a tileserver using [tileserver-gl](https://tileserver.readthedocs.io/en/latest/) as well as a static file server using [http-server](https://www.npmjs.com/package/http-server) for styles, fonts, and sprites.

Vector tiles come from [Geofabrik](https://download.geofabrik.de/north-america/us/massachusetts.html) and sprites from [Versatiles](https://github.com/versatiles-org/versatiles-style?tab=readme-ov-file#use-styles-for-versatilesorg).


## Running the server

Get the latest vector tiles.

```
%> ./update-data
```

Run docker compose.

```
%> docker compose -f deploy/docker-compose.yml up --build
```

You can then use [maplibre-gl](https://maplibre.org/maplibre-gl-js/docs/).

```javascript
new maplibregl.Map({
  ...,
  style: 'http://localhost:8888/style.json',
});
```

## Roadmap

* Serve fonts and sprites out of tileserver-gl and remove the static server
* Create glyphs for [Inter](https://fonts.google.com/specimen/Inter) so our font styles match the brand
* Add New Hampshire and Rhode Island
  * It doesn't look like simply adding multiple states works as the tiles overlap
  * Either use the entire NE (which is a 1.5GB file) or figure out how to combine multiple states 