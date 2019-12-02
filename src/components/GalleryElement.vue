<template lang="html">

  <li>
    <div class="">
      <img class="gridImage" :id="image.rover.name + image.id" :src="image.img_src" alt="">
    </div>
    <div class="infoPic">
      <span>ROVER: {{image.rover.name}}</span>
      <span>CAMERA: {{image.camera.full_name}}</span>
      <span>ID: {{image.id}}</span>
    </div>

  </li>

</template>

<script>
export default {
  name: "gallery-element",
  props: ["image"],

}

</script>


<style lang="css" scoped></style>
