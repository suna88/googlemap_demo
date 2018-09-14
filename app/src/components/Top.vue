<template>
  <div class="container">
    <h3>テストあぷり</h3>
    <GmapMap
      :center="{lat:35.6808, lng:139.719}"
      :zoom="18"
      map-type-id="terrain"
      class="map"
    >
      <GmapMarker
        :key="index"
        v-for="(m, index) in markers"
        :position="m.position"
        :clickable="true"
        :draggable="true"
        @click="center=m.position"></GmapMarker>
    </GmapMap>
    <button @click="move">スタート</button>
  </div>
</template>
<style scoped lang="scss">
  .container {
    text-align: center;

    .map {
      width: 700px;
      height: 500px;
      margin: 0 auto;
    }

  }

</style>

<script>
  // eslint-disable-next-line indent
  /* eslint-disable indent */

  export default {
    name: 'Top',
    data() {
      return {
        msg: 'message',
        markers: [{
          position: {
            lat: 35.6,
            lng: 140
          }
        }, {
          position: {
            lat: 35.6808,
            lng: 139.719
          }
        }]
      }
    },
    methods: {
      move: function () {
        setInterval(() => {
          this.markers[1].position.lat += 0.00001
          this.markers[1].position.lng += 0.000003
          console.log(this.markers[1].position.lng)
        }, 500)
      }
    }
  }
</script>
