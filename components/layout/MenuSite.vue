<template>
  <div class="nav-container">
    <div class="menu-btn d-flex align-items-center" @click="toogleMenu">
      <div class="hamburger mr-2">
        <span :class="{change : menuListVisible}" />
        <span :class="{change : menuListVisible}" />
        <span :class="{change : menuListVisible}" />
      </div>
      <div class="menu-txt">
        MENU
      </div>
    </div>
    <div class="list-wrap">
      <NuxtLink
        v-for="(item, index) in menuList"
        :key="index"
        :to="item.to"
        class="list d-flex align-items-center position-absolute"
        :style="calculateButtonStyle(index)"
      >
        {{ item.name }}
      </NuxtLink>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      menuListVisible: false,
      menuList: [
        { name: 'Home', to: '/' },
        { name: 'Dynamic Route', to: '/dynamic-route' },
        { name: 'Sprite Animation', to: '/sprite-animation' }
      ]
    }
  },
  methods: {
    toogleMenu () {
      this.menuListVisible = !this.menuListVisible
    },
    calculateButtonStyle (index) {
      return {
        top: `${this.menuListVisible ? (index + 1) * 40 : 30}px`,
        opacity: `${this.menuListVisible ? 1 : 0}`,
        'transition-delay': `${index * 0.1}s`,
        'pointer-events': `${this.menuListVisible ? 'auto' : 'none'}`
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  .nav-container {
    position: absolute;
    top: 30px;
    left: 30px;
    color: #93e4ff;
    font-family: 'Saira Semi Condensed', sans-serif;
    font-weight: 200;
    font-size: 1.2rem;

    .menu-btn {
      cursor: pointer;
      pointer-events: auto;

      .menu-txt {
        color: #ffffff;
        font-size: 0.9rem;
        letter-spacing: 6px;
      }
    }

    .hamburger {
      span {
        display: block;
        background: #93e4ff;
        width: 20px;
        height: 2px;
        margin: 4px 0;
        transition: 0.4s;

        &.change {
          background: #ff5454;

          &:nth-child(1) {
            -webkit-transform: rotate(-45deg) translate(-5px, -2px);
            transform: rotate(-45deg) translate(-6px, 2px);
          }
          &:nth-child(2) {
            opacity: 0;
          }
          &:nth-child(3) {
            -webkit-transform: rotate(45deg) translate(-6px, -3px);
            transform: rotate(45deg) translate(-6px, -3px);
          }
        }
      }
    }

    .list-wrap {
      .list {
        padding: 4px 7px;
        white-space: nowrap;
        color: #93e4ff;
        text-decoration: none !important;
        transition: all 0.3s ease-out;

        &::before {
          content: '';
          display: inline-block;
          width: 0px;
          height: 2px;
          background-color: #93e4ff;
          transition: all 0.3s ease-out;
        }

        &.nuxt-link-exact-active {
          color: #ff5454;
          pointer-events: none !important;

          &::before {
            width: 25px;
            margin-right: 0.5rem;
            background-color: #ff5454;
          }
        }

        &:hover:not(.nuxt-link-exact-active) {
          background-color: rgba($color: #484848, $alpha: 0.6);
          border-radius: 4px;
        }
      }
    }
  }
</style>
