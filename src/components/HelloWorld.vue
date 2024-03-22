<!-- eslint-disable vue/valid-v-for -->
<!-- eslint-disable vue/no-v-for-template-key -->
<template>
  <v-container>
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
          La aplicacion esta construida con el framework Vue.js
        </h1>

        <p class="subheading font-weight-regular">
          La hoja de estilos esta constrida sobre la libreria Vuetify.js
          <br />please join our online
        </p>
      </v-col>
    </v-row>
    <v-row>
      <v-card
        class="mx-auto"
        height="300px"
        width="500px"
        style="margin-top: -70px"
      >
        <v-card-title>
          <v-col class="mb-5" cols="12">
            <h2 class="headline font-weight-bold mb-3">Ciclo for en html</h2>
          </v-col>
        </v-card-title>
        <v-card-text style="padding: 0 20px">
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
        </v-card-text>
      </v-card>
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
