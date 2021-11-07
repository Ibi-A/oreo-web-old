<template>
  <b-modal :title="title" :id="'modal-' + postId + '-' + pictureId" size="xl" centered ok-only>
    <b-img
      :src="src"
      class="mb-3"
      fluid-grow
    />
    <p>{{ description }}</p>
  </b-modal>
</template>

<script lang="ts">

export default {
    props: {
        postId: Number,
        pictureId: Number, 
        title: String,
        description: String,
        src: String,
    }
}
</script>