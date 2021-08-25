<template>
  <div class="cases">
    <a v-for="item in cases" :key="item.id" :href="`${item.slug}`" class="case">
      <div class="caption">
        <span> {{ item.title }}</span>
      </div>
      <div class="background">
        <img src="http://placekitten.com/300/300">
      </div>
    </a>
  </div>
</template>

<script>
export default {
  data () {
    return {
      cases: []
    }
  },
  async fetch () {
    this.cases = await this.$axios.$get('https://fabiovaz.herokuapp.com/jobs')
  }
}
</script>

<style lang="scss">
.cases {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-auto-rows: auto;
  grid-gap: 30px;
  .case {
    position: relative;
    display: block;
    width: 100%;
    height: 200px;
    background: red;
    .caption {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%)
    }
    .background {
      width: 100%;
      height: 100%;
      img {
        width: 100%;
        height: 100%;
        object-fit: cover;
      }
    }
  }
}
</style>
