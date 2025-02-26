<template>
  <div id="app">
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
/* 可以在这里添加额外的局部样式 */
</style>