<template>
  <div class="main">
    <Nuxt />
    <menu-site />
  </div>
</template>

<script>
import MenuSite from '~/components/layout/MenuSite'

export default {
  components: {
    MenuSite
  }
}
</script>

<style lang="scss" scoped>
  .main {
    width: 100vw;
    height: 100vh;
    background-color: #292929;
    overflow: hidden;
    position: relative;
  }
</style>

<style lang="scss">
  .page {
    width: 100%;
    height: 100%;

    .content {
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgb(0,0,0);
      background: -moz-linear-gradient(180deg, rgba(0,0,0,0.5) 0%, rgba(0,0,0,0.2) 100%);
      background: -webkit-linear-gradient(180deg, rgba(0,0,0,0.5) 0%, rgba(0,0,0,0.2) 100%);
      background: linear-gradient(180deg, rgba(0,0,0,0.5) 0%, rgba(0,0,0,0.2) 100%);
      filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#000000",endColorstr="#000000",GradientType=1);

      h1 {
        color: #FFFFFF;
        font-family: 'Saira Semi Condensed', sans-serif;
        font-weight: 800;
        font-size: 4rem;
      }
    }
  }
</style>

<style>
  .slide-left-leave-active,
  .slide-right-leave-active {
    position: absolute;
    width: 100vw;
  }
  .slide-left-enter-active {
    animation: slide-from-right 1.6s;
  }
  .slide-left-leave-to {
    animation: slide-to-left 1s;
  }
  .slide-right-enter-active {
    animation: slide-from-left 1.6s;
  }
  .slide-right-leave-to {
    animation: slide-to-right 1s;
  }
  @keyframes slide-to-left {
    0% {
      opacity: 1;
      transform: scale(1);
    }
    50% {
      opacity: 0.5;
      transform: scale(0.5);
    }
    100% {
      opacity: 0;
      transform: translate(-40%, 0) scale(0.5);
    }
  }
  @keyframes slide-to-right {
    0% {
      opacity: 1;
      transform: scale(1);
    }
    50% {
      opacity: 0.5;
      transform: scale(0.5);
    }
    100% {
      opacity: 0;
      transform: translate(40%, 0) scale(0.5);
    }
  }
  @keyframes slide-from-left {
    0% {
      opacity: 0;
      transform: translate(-40%, 0) scale(0.5);
    }
    40% {
      opacity: 0;
      transform: translate(-40%, 0) scale(0.5);
    }
    80% {
      opacity: 0.5;
      transform: scale(0.5);
    }
    100% {
      opacity: 1;
      transform: scale(1);
    }
  }
  @keyframes slide-from-right {
    0% {
      opacity: 0;
      transform: translate(40%, 0) scale(0.5);
    }
    40% {
      opacity: 0;
      transform: translate(40%, 0) scale(0.5);
    }
    80% {
      opacity: 0.5;
      transform: scale(0.5);
    }
    100% {
      opacity: 1;
      transform: scale(1);
    }
  }
</style>
