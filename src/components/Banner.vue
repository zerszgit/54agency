<template>
  <div ref="container" :class="$style.container">
    <Header />
    <h1 ref="title" :class="$style.title">54 AGENCY</h1>
    <div class="text-heading">
      <p ref="text" :class="$style.text">
        Создаем цифровые продукты, которые покоряют с первого клика
      </p>
    </div>
    <a ref="link" :class="$style.link" href="#"
      >Обсудить ваш проект <img src="/img/arrow-right.svg" alt="icon"
    /></a>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import gsap from "gsap";
import SplitText from "gsap-trial/SplitText";

export default {
  components: {
    Header,
  },
  mounted() {
    gsap.registerPlugin(SplitText);

    const title = this.$refs.title;
    const text = this.$refs.text;
    const link = this.$refs.link;

    gsap.from(title, {
      y: 170,
      duration: 2,
      delay: 1,
      ease: "power4",
      color: "#FFF",
    });

    const childSplit = new SplitText(text, {
      type: "lines",
      linesClass: "split-child",
    });

    const parentSplit = new SplitText(text, {
      // type: "lines",
      linesClass: "split-parent",
    });

    gsap.from(childSplit.lines, {
      duration: 2,
      yPercent: 100,
      ease: "power4",
      stagger: 0.1,
      delay: 1.25,
    });

    gsap.from(parentSplit.lines, {
      duration: 2,
      yPercent: 100,
      ease: "power4",
      stagger: 0.1,
      delay: 1.25,
    });

    gsap.from(link, {
      duration: 0.8,
      opacity: 0,
      yPercent: 100,
      ease: "power",
      stagger: 0.02,
      delay: 1.75,
    });
  },
};
</script>

<style lang="scss" module>
.container {
  height: 100vh;
  padding: 3rem 0;
  display: flex;
  flex-direction: column;
  .title {
    font-size: 36vh;
    letter-spacing: -1.5rem;
    white-space: nowrap;
    font-weight: 700;
    color: rgba(128, 128, 128, 1);
    flex: 1 1 auto;
    margin: 2rem 0 0 0;
  }
  .text {
    max-width: 59.375rem;
    font-size: 3.375rem;
    margin: 0 0 2rem 0;
    position: relative;
    overflow: hidden;
  }
  .text {
    div {
      position: relative;
      margin: 0;
    }
  }

  .link {
    display: flex;
    gap: 0.5rem;
    font-size: 1.5rem;
    align-items: center;
  }
}
</style>

<style>
.split-parent {
  overflow: hidden;
}
.split-child {
  display: inline-block;
}
</style>
