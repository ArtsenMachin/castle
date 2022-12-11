<template>
    <section>
        <h1>Места и достопримечательности</h1>
        <v-card
            flat
            outlined
            rounded
            class="mt-8"
        >
            <DesctopZones
                v-if="!isMobile"
            />
            <MobileZones
                v-else
            />
        </v-card>
    </section>
</template>

<script>
import DesctopZones from './DesctopZones.vue';
import MobileZones from './MobileZones.vue';

export default {
  components: { DesctopZones, MobileZones },
  name: 'ZonesMapper',
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.xs;
    },
  },
};
</script>
<style>
.v-expansion-panel-header > *:not(.v-expansion-panel-header__icon) {
    flex: unset !important
}
</style>
