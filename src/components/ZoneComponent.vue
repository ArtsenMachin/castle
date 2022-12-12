<template>
    <section>
    <v-card flat>
        <v-card-title class="pt-2">
            {{ zone.name }}
        </v-card-title>
        <v-card-text>
            {{ zone.text }}
        </v-card-text>
        <v-card-text
        v-if="i !== 5"
        class="d-flex flex-row aling-center justify-center"
        >
            <v-img
                :src="require(`../assets/${i+1}.jpg`)"
                class="mx-auto"
                width="100%"
                contain
            />
        </v-card-text>
    </v-card>
    </section>
</template>

<script>
export default {
  name: 'ZoneComponent',
  props: {
    zone: {
      type: Object,
      default: () => ({}),
    },
    i: {
      type: Number,
      default: null,
    },
  },
};
</script>
