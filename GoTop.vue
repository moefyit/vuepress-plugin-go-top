<template>
  <div id="goTop" :class="catStyle" @click="goTop"></div>
</template>

<script>
  export default {
    name: "GoTop",
    data() {
      return {
        visible: false,
        interval: null,
        isMoving: false,
        visibilityHeight: 500,
        catStyle: "hide-cat"
      }
    },
    mounted() {
      window.addEventListener('scroll', this.handleScroll, true)
    },
    destroyed() {
      window.removeEventListener('scroll', this.handleScroll)
      if (this.interval) {
        clearInterval(this.interval)
      }
    },
    methods: {
      handleScroll() {
        if (!this.isMobile()) {
          this.visible = window.pageYOffset > this.visibilityHeight
          this.catStyle = this.visible ? "show-cat" : "hide-cat"
        }
      },
      goTop() {
        if (this.isMoving) return
        const start = window.pageYOffset
        let i = 0
        this.isMoving = true
        this.interval = setInterval(() => {
          const next = Math.floor(this.easeInOutQuad(10 * i, start, -start, 500))
          if (next <= 0) {
            window.scrollTo(0, 0)
            clearInterval(this.interval)
            this.isMoving = false
          } else {
            window.scrollTo(0, next)
          }
          i++
        }, 16.7)
      },
      easeInOutQuad (t, b, c, d) {
        if ((t /= d / 2) < 1) return c / 2 * t * t + b
        return -c / 2 * (--t * (t - 2) - 1) + b
      },
      isMobile() {
        return /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)
      }
    },

  }
</script>

<style scoped>
  @keyframes offsets{
    0%{
      transform: translateY(1px);
    }
    20%{
      transform: translateY(2px);
    }
    40%{
      transform: translateY(3px);
    }
    60%{
      transform: translateY(2px);
    }
    80%{
      transform: translateY(1px);
    }
    100%{
      transform: translateY(0px);
    }
  }
  @-webkit-keyframes offsets{
    0%{
      transform: translateY(0px);
    }
    20%{
      transform: translateY(2px);
    }
    40%{
      transform: translateY(4px);
    }
    60%{
      transform: translateY(4px);
    }
    80%{
      transform: translateY(2px);
    }
    100%{
      transform: translateY(0px);
    }
  }
  .show-cat {
    cursor: pointer;
    position: fixed;
    right: 80px;
    top: -200px;
    z-index: 0;
    width: 70px;
    height: 900px;
    background: url(assets/go_top.png);
    opacity: 1;
    transition: all .5s ease-in-out;
    animation-name: offsets;
    animation-duration: 3s;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    -webkit-animation-name: offsets;
    -webkit-animation-duration: 3s;
    -webkit-animation-timing-function: linear;
    -webkit-animation-iteration-count: infinite;
  }
  .hide-cat {
    cursor: pointer;
    position: fixed;
    right: 80px;
    top: -900px;
    z-index: 0;
    width: 70px;
    height: 900px;
    background: url(assets/go_top.png);
    opacity: 1;
    transition: all .5s ease-in-out;
  }
</style>
