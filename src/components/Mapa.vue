<template>
  <v-container>
  <v-card>
    <v-card-text>
    <l-map
      @click="agregaMarcador"
      style="height: 400px"
      :zoom="zoom"
      :center="center"
    >
      <l-tile-layer :url="url" :attribution="attribution"></l-tile-layer>
      <l-marker
        v-for="marker in marcadores"
        :key="marker.id"
        :lat-lng="marker.pos"
      >
        <l-popup>
          <div @click="innerClick">
            {{ marker.desc }}
            <p v-show="showParagraph"></p>
          </div>
        </l-popup>
      </l-marker>
    </l-map>
  </v-card-text>
  </v-card>
</v-container>
</template>
<script>
import { LMap, LTileLayer, LMarker, LPopup } from "vue2-leaflet";
export default {
  components: {
    LMap,
    LTileLayer,
    LMarker,
    LPopup,
  },

  data: () => ({
    showParagraph: false,
    coordenadas: [],
    datos: [],
    saludo: "hola",
    marcadores: [],
    url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
    attribution:
      '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
    zoom: 10,
    center: [ -36.632060059770694, -56.70318603515626],
    markerLatLng: [ -36.632060059770694, -56.70318603515626],
    imgIcon: require("leaflet/dist/images/marker-icon.png"),
  }),
  methods: {
    agregaMarcador(event) {
      this.marcadores = [];
      this.marcadores.push({ pos: event.latlng, desc: "Agregado!!" });

      console.log(this.marcadores);
      //  console.log(this.marcadores[0].pos.lng);
      this.datos.Latitud = this.marcadores[0].pos.lat;
      this.datos.Longitud = this.marcadores[0].pos.lng;
      console.log(this.datos.Longitud);
      console.log(this.datos.Latitud);
    },
    zoomUpdate(zoom) {
      this.currentZoom = zoom;
    },
    centerUpdate(center) {
      this.currentCenter = center;
    },
    showLongText() {
      this.showParagraph = !this.showParagraph;
    },
    innerClick() {
      alert("Click!");
    },
  },
};
</script>
