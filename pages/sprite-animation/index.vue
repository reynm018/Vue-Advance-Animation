<template>
  <div class="page">
    <div class="content d-flex align-items-center justify-content-center">
      <h1>
        Sprite Animation
      </h1>
    </div>
  </div>
</template>

<script>
export default {
  transition (to, from) {
    const pages = ['index', 'dynamic-route', 'sprite-animation']
    const transitionName = (!from || !to) ? 'slide-left' : (pages.indexOf(to.name) > pages.indexOf(from.name)) ? 'slide-left' : 'slide-right'
    return {
      name: transitionName,
      mode: ''
    }
  }
}
</script>

<style lang="scss" scoped>
  .page {
    background: rgb(80,89,255);
    background: -moz-linear-gradient(180deg, rgba(80,89,255,1) 0%, rgba(25,204,241,1) 100%);
    background: -webkit-linear-gradient(180deg, rgba(80,89,255,1) 0%, rgba(25,204,241,1) 100%);
    background: linear-gradient(180deg, rgba(80,89,255,1) 0%, rgba(25,204,241,1) 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#5059ff",endColorstr="#19ccf1",GradientType=1);
  }
</style>
