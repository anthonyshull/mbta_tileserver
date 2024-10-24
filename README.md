# MBTA TILESERVER

Runs a tileserver using [tileserver-gl](https://tileserver.readthedocs.io/en/latest/) as well as a static file server using [http-server](https://www.npmjs.com/package/http-server) for styles, fonts, and sprites.

Vector tiles come from [Geofabrik](https://download.geofabrik.de/north-america/us/massachusetts.html) and sprites from [Versatiles](https://github.com/versatiles-org/versatiles-style?tab=readme-ov-file#use-styles-for-versatilesorg).

```
%> docker compose -f deploy/docker-compose.yml up
```

You can then use [maplibre-gl](https://maplibre.org/maplibre-gl-js/docs/) like so:

```javascript
new maplibregl.Map({
  ...,
  style: 'http://localhost:8888/style.json',
});
```