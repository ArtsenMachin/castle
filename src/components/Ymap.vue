<template>
    <section>
        <yandex-map
            :coords="[59.953913, 31.038576]"
            zoom="17"
            style="height: 600px;"
            :cluster-options="{
                1: {clusterDisableClickZoom: true}
            }"
            @map-was-initialized="initHandler"
            :settings="setting"
        >
            <ymap-marker
                v-for="(item, i) in items"
                :key="i"
                :markerId="i"
                marker-type="Placemark"
                :coords="item.coords"
                :hint-content="item.name"
                :balloon-template="content(i)"
                cluster-name="1"
                :icon="{content: `${i+1}`}"
            ></ymap-marker>
        </yandex-map>
    </section>
</template>

<script>
import { yandexMap, ymapMarker } from 'vue-yandex-maps';
/* eslint-disable global-require */
/* eslint-disable import/no-dynamic-require */
export default {
  name: 'Ymap',
  components: { yandexMap, ymapMarker },
  props: {
    items: {
      type: Array,
      default: () => ([]),
    },
  },
  data: () => ({
    setting: {
      apiKey: '',
      lang: 'ru_RU',
      enterprise: false,
      version: '2.1',
    },
  }),
  computed: {
    content() {
      return (i) => {
        if (i !== 5) {
          const src = require(`../assets/${i + 1}.jpg`);
          return `
                <div style="max-width:250px">
                    <h1>${this.items[i].name}</h1>
                    <img src="${src}" style="max-height:200px"/>
                    <p>${this.items[i].text}</p>
                </div>
            `;
        }
        return `
            <div style="max-width:250px">
                <h1>${this.items[i].name}</h1>
                <p>${this.items[i].text}</p>
            </div>
            `;
      };
    },
  },
};
</script>
