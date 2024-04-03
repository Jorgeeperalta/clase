<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <br />
        <br />
        <br />
        <br />
        <br />
        <h1>LOGIN</h1>
        <v-btn outlined color="blue" @click="ingresar">INGRESAR</v-btn>
        <br />
        <br />
        <v-btn outlined color="red" @click="mapa">MAPA</v-btn>
        <br />
        <br />
        <v-btn outlined color="green" @click="datos">Tabla</v-btn>
        <br />
        <br />
        <v-btn outlined color="green" @click="traerDatosApi">trer datos desde api</v-btn>
        <br><br>
        <v-btn @click="grafico">Grafico de barras</v-btn>
      </v-col>
      {{ comentarios }}
    </v-row>
  </v-container>
</template>
<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Login",
  data: () => ({
    comentarios: [],
  }),
  methods: {
    grafico(){
      this.$router.push("/graficos");
      this.$store.state.btnLogin = true;
    },
    traerDatosApi(){
      fetch('https://jsonplaceholder.typicode.com/comments')
      .then(response => response.json())
      .then(json => (this.comentarios=json))
      .then(json => console.log(json))
    },
    mapa() {
      this.$router.push("/about");
      this.$store.state.btnLogin = true;
    },
    ingresar() {
      this.$router.push("/");
      this.$store.state.btnLogin = true;
    },
    datos() {
      this.$router.push("/datos");
      this.$store.state.btnLogin = true;
    },
  },
};
</script>