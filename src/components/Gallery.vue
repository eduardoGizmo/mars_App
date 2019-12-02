<template>

      <ul class="grid-gallery">
        <gallery-element v-for="(image, index) in gallery"
                         :image="image" :key="index">
        </gallery-element>
      </ul>

</template>

<script>
import GalleryElement from './GalleryElement.vue'


export default {
  name: 'gallery',
  props: ["gallery"],
  components: {
    "gallery-element": GalleryElement,
  },





}

</script>

<style scoped></style>
