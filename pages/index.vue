<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
    <v-container fluid>
      <v-row dense>
        <v-col
          v-for='anime in animes'
          :key='anime.id'
          lg='3'
          md='6'
          xs='12'
        >
          <anime-card
            class='ma-3'
            :id='anime.id'
            :name='anime.name'
            :number='anime.number'
            :type='anime.type'
            :image='anime.image'
            :link='anime.link'
          >

          </anime-card>
        </v-col>

      </v-row>
    </v-container>
    </v-flex>
  </v-layout>
</template>

<script>

import AnimeCard from '~/components/AnimeCard.vue'

export default {
  components: {
    AnimeCard
  },
  data () {
    return {
      animes: [
        {
          id: 1,
          name: 'naruto',
          number: 1,
          type: 'episodio',
          image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
          link: 'naruto'
        },
        {
          id:2,
          name: 'afro samurai',
          number: null,
          type: 'pelicula',
          image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
          link: 'afro-samurai'
        },
        {
          id:3,
          name: 'afro samurai',
          number: null,
          type: 'pelicula',
          image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg'
        }
      ]
    }
  }
}
</script>
