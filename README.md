# Google Maps API tutorial
Introductory Google Maps Tutorial

Clone this repository, and follow along by adding these into the existing code base:  


First we will add a stylesheet for the map, and include the script tag for Google Maps API. Note that the query parameter `key` should be the key you signed up for with Google (sign up with a key here: https://developers.google.com/maps/documentation/javascript/
```html
<link rel="stylesheet" href="map.css">

<div id="map"></div>
<script src="https://maps.googleapis.com/maps/api/js?key=INSERT_YOUR_KEY_HERE&v=3.exp&libraries=visualization"></script>
<script src="map.js"></script>
```

In our `map.js` file - the stylesArray includes some defaults for how our map will look. Feel free to make it your own! Add the following code after the stylesArray:

```js
var mapOptions = {
  zoom: 15,
  styles: stylesArray,
  center: new google.maps.LatLng(47.618217, -122.351832),
  mapTypeId: google.maps.MapTypeId.STREET,
  zoomControl: true,
  zoomControlOptions: {
    position: google.maps.ControlPosition.RIGHT_CENTER
  }
}

var map = new google.maps.Map(document.getElementById('map'), mapOptions);
```
Make the map responsive:
```js
google.maps.event.addDomListener(window, 'resize', function() {
  var center = map.getCenter();
  google.maps.event.trigger(map, 'resize');
  map.setCenter(center);
});
```
After demoing that it works, add a marker!
```js
var marker = new google.maps.Marker({
  position: {lat: 47.618217, lng: -122.351832},
  map: map,
});
```
Now in our map.css file - add some final styles
```css
#map {
  margin: 10%;
  padding: 25% 0;
  border: 10px solid green;
}

```

