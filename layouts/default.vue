<template>
  <v-app class="app">
    公開までの間、ただいま準備中です。今しばらくお待ち下さい。
    <!--div class="d-sm-flex">
      <SideNavigation
        @openNavi="showNavi"
        @closeNavi="hideNavi"
        :isMobile="isMobile"
        :isNaviOpen="isNaviOpen"
        :class="{open: isMobile && isNaviOpen}"
      />
      <div class="mainContainer px-4">
        <v-container>
          <nuxt />
        </v-container>
      </div>
    </div-->
  </v-app>
</template>
<script>
import SideNavigation from '@/components/SideNavigation'

export default {
  components: {
    SideNavigation
  },
  data() {
    return {
      isNaviOpen: false,
      isMobile: false
    }
  },
  mounted() {
    window.addEventListener('resize', this.handleResize)
    this.handleResize()
  },
  destroyed() {
    window.removeEventListener('resize', this.handleResize)
  },
  methods: {
    handleResize() {
      this.isMobile = window.innerWidth < 600
    },
    showNavi() {
      this.isNaviOpen = true
    },
    hideNavi() {
      this.isNaviOpen = false
    }
  }
}
</script>

<style>
.app {
  background-color: inherit !important;
}
.mainContainer {
  flex: 1 1 auto;
  overflow-x: hidden;
  overflow-y: auto;
  height: 100vh;
}
.open {
  height: 100vh;
}
</style>
