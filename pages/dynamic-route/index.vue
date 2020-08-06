<template>
  <div class="page">
    <div class="content d-flex align-items-center justify-content-center">
      <h1>
        Dynamic route with transition
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
    background: rgb(255,82,245);
    background: -moz-linear-gradient(180deg, rgba(255,82,245,1) 0%, rgba(119,209,255,1) 100%);
    background: -webkit-linear-gradient(180deg, rgba(255,82,245,1) 0%, rgba(119,209,255,1) 100%);
    background: linear-gradient(180deg, rgba(255,82,245,1) 0%, rgba(119,209,255,1) 100%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#ff52f5",endColorstr="#77d1ff",GradientType=1);
  }
</style>
