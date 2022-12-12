<template>
    <section>
        <v-expansion-panels accordion>
        <v-expansion-panel
        v-for="(item, i) in zones"
        :key="i"
        >
            <v-expansion-panel-header
                class="d-flex flex-row justify-start"
            >
            <div>
                <v-btn
                    elevation="0"
                    fab
                    outlined
                    x-small
                >
                    {{ i + 1}}
                </v-btn>
            </div>

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
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              <zone-component
                :zone="item[i]"
                :i="i"
              />
            </v-expansion-panel-content>
        </v-expansion-panel>
    </v-expansion-panels>
    </section>
</template>

<script>
import ZoneComponent from './ZoneComponent.vue';

export default {
  components: { ZoneComponent },
  name: 'MobileZones',
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
