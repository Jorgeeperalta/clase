<!-- eslint-disable vue/valid-v-for -->
<!-- eslint-disable vue/no-v-for-template-key -->
<template>
  <v-container>
    <br /><br />
    <br /><br />
    <br /><br />
    <v-row class="text-center">
      <v-col cols="12">
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        />
      </v-col>

      <v-col class="mb-4">
        <h1 class="display-2 font-weight-bold mb-3">
          La aplicacion esta construida con el framework Vue.js + deploy Versel
        </h1>

        <p class="subheading font-weight-regular">
          La hoja de estilos esta constrida sobre la libreria Vuetify.js
          <br />please join our online
        </p>
        <p class="subheading font-weight-regular">
          <b>Ciclo for en html</b>
        </p>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <v-row justify="center">
          <v-list three-line>
            <template v-for="numero in numeros">
              <v-list-item :key="numero.id">
                {{ numero.name }} {{ numero.id }}
              </v-list-item>
            </template>
          </v-list>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",

  data: () => ({
    numeros: [],
  }),
  created() {
    this.initialize();
  },
  methods: {
    initialize() {
      this.numeros = [
        { id: 1, name: "numero uno" },
        { id: 2, name: "numero dos" },
        { id: 3, name: "numero tres" },
      ];
    },
    login() {
      this.$router.push("/login");
    },
  },
};
</script>
