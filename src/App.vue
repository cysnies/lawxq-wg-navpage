<template>
  <div id="app" style="display: flex;">
    <Sidebar @load-page="loadPage" @sidebar-toggle="handleSidebarToggle" />
    <div class="iframe-container">
      <iframe :src="currentUrl" frameborder="0"></iframe>
    </div>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue';

export default {
  components: {
    Sidebar,
  },
  data() {
    return {
      currentUrl: '',
      sidebarCollapsed: false,
    };
  },
  methods: {
    loadPage(url) {
      this.currentUrl = url;
    },
    handleSidebarToggle(isCollapsed) {
      this.sidebarCollapsed = isCollapsed;
    },
  },
};
</script>

<style scoped>
#app {
  display: flex;
  height: 100vh;
  width: 100vw;
}
</style>