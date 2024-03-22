<template>
   <v-container>
      <v-row class="text-center">
         <v-col cols="12">
            <card>
               <h1>LOGIN</h1>
               <v-btn  @click="ingresar">INGRESAR</v-btn>
            </card>
         </v-col>
      </v-row>
   </v-container>
</template>
<script>
export default {
   // eslint-disable-next-line vue/multi-word-component-names
   name: 'Login',
   data: () => ({
   }),
   methods:{
      ingresar(){
         
         this.$router.push('/')
      }
   }
}
</script>