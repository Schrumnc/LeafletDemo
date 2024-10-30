# Leaflet Map Demo

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Leaflet Map Demo</title>
    <link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY=" crossorigin="" />
    <script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo=" crossorigin=""></script>
</head>
<body>
    <!--the web map will go here in the code-->
    <!--first, create a div to hold the map-->
    <div id="map" style="width: 900px; height: 600px"></div>

    <!--second, create a script to loads the leaflet js map-->
    <script>
        //now, working in JS
        //time to load the map

        // Create variable to hold map element, give initial settings to map
        var map = L.map('map',{
            center: [36.214039, -81.681719],
            zoom: 16
        });

        //add basemap tile service with L.Tilelayer class
        L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
            maxZoom: 20,
            attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
        }).addTo(map);

        //add placemarker with point coordinate pair here
        // Create point feature for Rankin Science West
        var myDataPoint = L.marker([36.214039, -81.681719]).addTo(map);

        //add polyline feature now
        // Create line feature for the Route from Rankin Science West to Espresso News, style and add to map
        var myDataLine = L.polyline([
            [36.214314, -81.681692], 
            [36.215239, -81.682050], 
            [36.215721, -81.682489], 
            [36.216385, -81.683184], 
            [36.216900, -81.682599], 
            [36.217805, -81.684187], 
            [36.218047, -81.683998]
        ], {
            color: 'darkblue', 
            weight: 5, 
        }).addTo(map);

        // Create area feature for Espresso News, style and add to map
        var myArea = L.polygon([
            [36.218060, -81.684023], 
            [36.218112, -81.683971], 
            [36.218077, -81.683912], 
            [36.218034, -81.683960]
        ], {
            color: 'darkblue', 
            weight: 5
        }).addTo(map);
    </script>
</body>
</html>

