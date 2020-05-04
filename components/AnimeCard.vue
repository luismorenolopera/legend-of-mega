<template>
    <v-card
    class='mx-auto'
    max-width='400'
  >
    <v-img
      class='white--text align-end'
      max-height="400"
      :src='image'
    >
      <v-card-title>{{name}}</v-card-title>
      <v-card-subtitle>{{type}} {{number}}</v-card-subtitle>
    </v-img>

    
  </v-card>
</template>

<script>
export default {
    props: {
        id: Number,
        name: String,
        number: Number,
        type: String,
        image: String
    }
}
</script>