<template>
  <div class="about">
    <h1>This is a map</h1>
    <div id="map"></div>
  </div>
</template>

<style>
body {
  margin: 20;
  padding: 20;
}
#map {
  height: 400px;
  width: 100%;
}
</style>

<script>
export default {
  data: function() {
    return {
      places: [
        {
          lng: -87.62,
          lat: 41.88,
          description: "Cloud Gate"
        },
        {
          lng: -87.62,
          lat: 41.87,
          description: "Art Institute"
        },
        {
          lng: -87.6,
          lat: 41.89,
          description: "Navy Pier"
        }
      ]
    };
  },
  mounted: function() {
    mapboxgl.accessToken =
      "pk.eyJ1IjoicGV0ZXJ4amFuZyIsImEiOiJjam94YWZieXExYnQ0M3BucXZwbmV2Y2VsIn0.pmLbX0YPw86c5r8YlyZr7w";
    var map = new mapboxgl.Map({
      container: "map", // container id
      style: "mapbox://styles/mapbox/streets-v9", // stylesheet location
      center: [this.places[0].lng, this.places[0].lat], // starting position [lng, lat]
      zoom: 12 // starting zoom
    });

    // this.places.forEach(function(place) {
    //   var popup =

    // });

    for (var i = 0; i < this.places.length; i++) {
      var place = this.places[i];
      var popup = new mapboxgl.Popup({ offset: 25 }).setText(place.description);
      var marker = new mapboxgl.Marker()
        .setLngLat([place.lng, place.lat])
        .setPopup(popup)
        .addTo(map);
    }

    map.addControl(
      new MapboxGeocoder({
        accessToken: mapboxgl.accessToken
      })
    );
  }
};
</script>
