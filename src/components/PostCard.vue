<template>
  <b-card>
    <b-carousel class="mb-3" controls indicators>
      <b-carousel-slide
        v-for="picture in pictures"
        :key="picture.id"
        :img-src="picture.src"
      >
        <h1>{{ picture.title }}</h1>
        <p>{{ picture.description }}</p>
      </b-carousel-slide>
    </b-carousel>

    <b-card-text>
      <h1></h1>
      <b-button v-b-toggle="'collapse-' + id" variant="link" class="mb-3"><h1>{{ title }}</h1></b-button>
      <b-collapse :id="'collapse-' + id">
        {{ description }}
      </b-collapse>
    </b-card-text>

    <template #footer>
      <b-badge>{{ date }}</b-badge>
    </template>
  </b-card>
</template>

<script lang="ts">
export default {
  props: {
    id: Number,
    date: String,
    title: String,
    description: String,
    pictures: [],
  },
};
</script>
