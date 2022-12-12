<template>
    <section>
        <v-tabs vertical>
            <v-tab
                v-for="(item, i) in zones"
                :key="i"
                class="d-flex flex-row justify-start"
            >
                <v-btn
                    elevation="0"
                    fab
                    outlined
                    x-small
                >
                    {{ i + 1}}
                </v-btn>
                <v-avatar
                    tile
                    size="40"
                    class="ml-4"
                    v-if="i !== 5"
                >
                    <img
                        :src="require(`../assets/${i+1}.jpg`)"
                    />
                </v-avatar>
                <span class='ml-4 subtitle-2'>
                    {{ item }}
                </span>
            </v-tab>
            <v-tab-item
                v-for="(item, i) in zones"
                :key="`items${i}`"
            >
                <zone-component
                  :zone="items[i]"
                  :i="i"
                />
            </v-tab-item>
        </v-tabs>
    </section>
</template>

<script>
import ZoneComponent from './ZoneComponent.vue';

export default {
  components: { ZoneComponent },
  name: 'DesctopZones',
  props: {
    items: {
      type: Array,
      default: () => ([]),
    },
  },
  data: () => ({
    zones: [
      'Головина башня',
      'Королевская башня',
      'Флажная башня',
      'Государева башня',
      'Светличная башня',
      'Меншикова башня',
      'Старая Тюрьма',
      'Новая тюрьма',
      'Мемориальный комплекс',
      'Мемориал “Клятва”',
      '4-ый Тюремный корпус крепости Орешек',
    ],
  }),
};
</script>
