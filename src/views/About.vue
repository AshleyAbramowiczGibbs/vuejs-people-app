<template>
  <div class="about">
    <h1>This is a map</h1>
    <div id='map'></div>
  </div>
</template>

<style>
body { margin:20; padding:20; }
#map { 

  height: 400px; 
  width:100%;

}
</style>



<script>
  export default {
    data: function() {
      return {
        arrayOfLocations: [
          { 
            Longitude: 1,
            Latitude: 2,
            Description: "Cloud Gate"
          },
          {
            Longitude: 1,
            Latitude: 2,
            Description: "Cloud Gate"
          },
          {
            Longitude: 1,
            Latitude: 2,
            Description: "Cloud Gate"
          },
          {
            Longitude: 1,
            Latitude: 2,
            Description: "Cloud Gate"
          }
        ]
      };
    },
    methods: {
      setPopText: function() {
        let description = "";
        for (let i = 0; i < arrayOfLocation.length; i++);


          return arrayOfLocations.description;
      }
    },
    mounted: function() {
      mapboxgl.accessToken = 'pk.eyJ1IjoicGV0ZXJ4amFuZyIsImEiOiJjam94YWZieXExYnQ0M3BucXZwbmV2Y2VsIn0.pmLbX0YPw86c5r8YlyZr7w';
      var map = new mapboxgl.Map({
container: 'map', // container id
style: 'mapbox://styles/mapbox/streets-v9', // stylesheet location
center: [-74.50, 40], // starting position [lng, lat]
zoom: 11 // starting zoom
});

      var popup = new mapboxgl.Popup({ offset: 25 })
      .setText();
      var marker = new mapboxgl.Marker()
      .setLngLat([-74.50, 40])
      .setPopup(popup)
      .addTo(map);


      map.addControl(new MapboxGeocoder({
        accessToken: mapboxgl.accessToken
      }));


    }
  };

</script>
