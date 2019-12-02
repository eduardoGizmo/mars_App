<template lang="html">
  <div class="selected-rover-info">
    <ul>
      <li><span>SOL: </span><span>{{this.gallery[0].sol}}</span></li>
        <li><span>EARTH DATE: </span><span>{{this.gallery[0].earth_date}}</span></li>
    </ul>
    <ul>
      <li><span>ROVER NAME: </span><span>{{this.gallery[0].rover.name.toUpperCase()}}</span></li>
      <li><span>ROVER ID: </span><span>{{this.gallery[0].rover.id}}</span></li>
      <li><span>LANDING DATE: </span><span>{{this.gallery[0].rover.landing_date}}</span></li>
      <li><span>LAUNCH DATE:</span> <span>{{this.gallery[0].rover.launch_date}}</span></li>
      <li><span>MAX DATE: </span><span>{{this.gallery[0].rover.max_date}}</span></li>
      <li><span>MAX SOL:</span> <span>{{this.gallery[0].rover.max_sol}}</span></li>
      <li><span>STATUS: </span><span>{{this.gallery[0].rover.status.toUpperCase()}}</span></li>
      <li><span>CAMERAS: </span><span>{{this.gallery[0].rover.cameras.length}}</span></li>
       <li><span>TOTAL PHOTOS:</span> <span>{{this.gallery[0].rover.total_photos}}</span></li>
    </ul>

  </div>
</template>

<script>

export default {
  name: "rover-details",
  props: ["gallery"],

}
</script>
