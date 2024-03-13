<template>
  <div ref="header" :class="$style.header">
    <img src="/img/logo.svg" alt="" />
    <nav :class="$style.links">
      <a href="#">Проекты</a>
      <a href="#">Услуги</a>
      <a href="#">Агенство</a>
      <a href="#">Контакты</a>
    </nav>
    <div :class="$style.contact">
      <img src="/img/telegram.svg" alt="" />
      <a href="#">Обсдить проект</a>
    </div>
  </div>
</template>

<script>
import gsap from "gsap";
export default {
  mounted() {
    const header = this.$refs.header;
    gsap.from(header, {
      opacity: 0,
      ease: "power",
      duration: 1,
      delay: 1,
    });
  },
};
</script>

<style lang="scss" module>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: fixed;
  top: 1.75rem;
  left: 50%;
  transform: translateX(-50%);
  width: 100%;
  @include container;
  z-index: 10;
  .links {
    a {
      margin: 0 1.5rem 0 1.5rem;
      font-size: 1.25rem;
    }
  }
  .contact {
    display: flex;
    align-items: center;
    a {
      color: $yellow;
      font-size: 1.25rem;
      margin: 0 0 0 1.5rem;
    }
  }
}
</style>
./Header.vue
