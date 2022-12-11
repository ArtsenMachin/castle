<template>
    <section>
        <v-row v-if="!isMobile">
            <v-col
                cols="12"
                md="5"
            >
                <v-img
                    :src="require('../assets/preview.jpeg')"
                    class="my-lg-3"
                    height="400"
                />
            </v-col>
            <v-col
                cols="12"
                md="6"
                class="ml-md-8"
            >
                <span class='display-3 font-weight-black'>
                    Крепость Орешек
                </span>
                <p class="mt-6">
                    {{ text }}
                </p>
            </v-col>
        </v-row>
        <v-row
            v-else
        >
            <v-col cols='12'>
                <span class='display-3 font-weight-black'>
                    Крепость Орешек
                </span>
            </v-col>
                <v-col
                cols="12"
            >
                <v-img
                    :src="require('../assets/preview.jpeg')"
                    class="my-lg-3"
                    height="400"
                />
            </v-col>
            <v-col cols='12'>
                <p class="mt-6">
                    {{ text }}
                </p>
            </v-col>
        </v-row>
    </section>
</template>

<script>
export default {
  name: 'MainInfo',
  data: () => ({
    text: `Свое название это фортификационное сооружение получило, по названию острова, 
    на котором она расположена – Ореховый, основана она в 1323 году. 
    Она находится на истоке реки Невы. Сохранилось немного памятников архитектуры, 
    представляющих собой оборонительное строение.
    Знаковое для горожан сооружении имеет форму вытянутого пятиугольника. 
    Каждый угол крепости венчает башня.`,
  }),
  computed: {
    isMobile() {
      return this.$vuetify.breakpoint.smAndDown;
    },
  },
};
</script>
