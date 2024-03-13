<template>
  <div :class="$style.app">
    <div ref="container" :class="$style.container">
      <div :class="$style.content">
        <Banner />
      </div>
    </div>
  </div>
</template>

<script>
import Banner from "@/components/Banner.vue";
export default {
  components: {
    Banner,
  },
};
</script>

<style lang="scss" module>
.app {
  background-color: $black;
  height: 300vh;
  .container {
    @include container;
    color: $white;
    .content {
      position: relative;
      .video {
        position: absolute;
        top: 10rem;
        right: 0;
        width: 20rem;
        height: 15rem;
        background-color: $yellow;
      }
    }
  }
}
</style>
