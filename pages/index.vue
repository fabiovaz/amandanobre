<template>
  <div class="cases">
    <div class="container">
      <div class="row">
        <div v-for="item in cases" :key="item.id" class="col-md-4">
          <a :href="`${item.slug}`" class="case">
            <div class="caption">
              <span> {{ item.title }}</span>
            </div>
            <div class="background">
              <img src="http://placekitten.com/300/300">
            </div>
          </a>
        </div>
      </div>
    </div>
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
  padding: 60px 0;
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
