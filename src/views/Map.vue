<template>
  <div id="map" class="map"></div>
</template>

<script>
import "ol/ol.css";
import { Map, View } from "ol";
import TileLayer from "ol/layer/Tile";
import OSM from "ol/source/OSM";

export default {
  mounted() {
    new Map({
      target: "map",
      layers: [
        new TileLayer({
          source: new OSM()
        })
      ],
      view: new View({
        center: [0, 0],
        zoom: 0
      })
    });
  }
};
</script>

<style>
#map {
  width: 100%;
  height: 100vh;
}

.ol-zoom {
  left: unset;
  right: 12px;
  top: 70%;
  transform: translateY(-70%);
}

.ol-zoom .ol-zoom-in {
  margin-bottom: 5px;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  font-size: 15pt;
}
.ol-zoom .ol-zoom-out {
  border-radius: 50%;
  margin-left: 5px;
  width: 40px;
  height: 40px;
  font-size: 12pt;
}
</style>
