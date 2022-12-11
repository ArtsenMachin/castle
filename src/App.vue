<template>
  <v-app>
    <v-app-bar
      app
      color="white"
      outlined
      :elevation="1"
    >
      <h3>Интерактивная карта Крепости Орешек</h3>
      <v-spacer></v-spacer>
      <img
       :src="require('./assets/icon.png')"
       width="32"
      />
    </v-app-bar>

    <v-main>
      <v-container fluid class="mt-4 pa-4 pa-md-8">
      <MainInfo/>
      <ZonesWrapper class="mt-8"/>
      </v-container>
    </v-main>
    <v-footer app class="d-flex flex-row justify-end">
        <span class="caption">
          ©️ Разработано Дмитрием Точёновым 2022
        </span>
    </v-footer>
  </v-app>
</template>

<script>
import MainInfo from './components/MainInfo.vue';
import ZonesWrapper from './components/ZonesWrapper.vue';

export default {
  name: 'App',

  components: {
    MainInfo,
    ZonesWrapper,
  },

  data: () => ({
    //
  }),
};
</script>
