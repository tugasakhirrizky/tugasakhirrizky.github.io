<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Add 3D terrain to a map</title>
<meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no">
<link href="https://api.mapbox.com/mapbox-gl-js/v2.11.0/mapbox-gl.css" rel="stylesheet">
<script src="https://api.mapbox.com/mapbox-gl-js/v2.11.0/mapbox-gl.js"></script>
<style>
body { margin: 0; padding: 0; }
#map { position: absolute; top: 0; bottom: 0; width: 100%; }
</style>
</head>
<body>
<div id="map"></div>

<script>
	mapboxgl.accessToken = 'pk.eyJ1IjoicmV6ZWtpcmV6ZWtpMSIsImEiOiJjbGJqaTNyNXMwZHBlM29ucmxvN2w0dWR3In0.YBdWa-MnwxkH-9LNtqnZtQ';
    const map = new mapboxgl.Map({
        container: 'map',
        zoom: 14,
        center: [-114.26608, 32.7213],
        pitch: 80,
        bearing: 41,
        // Choose from Mapbox's core styles, or make your own style with Mapbox Studio
        style: 'mapbox://styles/mapbox/satellite-streets-v12'
    });

    map.on('style.load', () => {
        map.addSource('mapbox-dem', {
            'type': 'raster-dem',
            'url': 'mapbox://mapbox.mapbox-terrain-dem-v1',
            'tileSize': 512,
            'maxzoom': 14
        });
        // add the DEM source as a terrain layer with exaggerated height
        map.setTerrain({ 'source': 'mapbox-dem', 'exaggeration': 1.5 });
    });
</script>

</body>
</html>
