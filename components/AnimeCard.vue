<template>
  <v-card
    class="mx-auto"
    max-width="400"
    @click="animeDetail()"
  >
    <v-img
      class="white--text align-end"
      max-height="400"
      :src="image"
    >
      <v-card-title>{{ name }}</v-card-title>
      <v-card-subtitle>{{ type }} {{ number }}</v-card-subtitle>
    </v-img>
  </v-card>
</template>

<script>
export default {
  props: {
    id: {
      type: Number,
      required: true
    },
    name: {
      type: String,
      required: true
    },
    number: {
      type: Number,
      required: true
    },
    type: {
      type: String,
      required: true
    },
    image: {
      type: String,
      required: true
    }
  },
  methods: {
    animeDetail () {
      this.$router.push({
        path: `watch/${this.type}/${this.name}/${this.number}`
      })
    }
  }
}
</script>
