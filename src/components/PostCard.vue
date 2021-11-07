<template>
  <b-card>
    <b-carousel class="mb-3" indicators controls fade>
      <b-carousel-slide
        v-for="picture in pictures"
        :key="picture.id"
        :img-src="picture.src"
        v-b-modal="'modal-' + id + '-' + picture.id"
      >
        <h1>{{ picture.title }}</h1>

        <picture-modal
          :post-id="id"
          :picture-id="picture.id"
          :title="picture.title"
          :description="picture.description"
          :src="picture.src"
        />
      </b-carousel-slide>
    </b-carousel>

    <b-card-text>
      <b-icon icon="arrow90deg-down" variant="primary"/>
      <b-button v-b-toggle="'collapse-' + id" variant="link" class="mb-3"
        ><h1>{{ title }}</h1></b-button
      >
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
import PictureModal from "./PictureModal.vue";

export default {
  components: {
    PictureModal,
  },
  props: {
    id: Number,
    date: String,
    title: String,
    description: String,
    pictures: [],
  },
};
</script>
