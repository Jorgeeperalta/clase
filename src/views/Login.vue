<template>
  <v-container>
    <v-row class="text-center">
      <v-col cols="12">
        <card>
          <h1>LOGIN</h1>
          <v-btn outlined color="blue" @click="ingresar">INGRESAR</v-btn>
          <br />
          <br />
          <v-btn outlined color="blue" @click="mapa">MAPA</v-btn>
        </card>
      </v-col>
    </v-row>
  </v-container>
</template>
<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Login",
  data: () => ({}),
  methods: {
    mapa() {
      this.$router.push("/about");
    },
    ingresar() {
      this.$router.push("/");
      this.$store.state.btnLogin = true;
    },
  },
};
</script>