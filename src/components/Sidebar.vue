<template>
  <div class="sidebar" :class="{ collapsed: isCollapsed }">
    <button class="toggle-button" @click="toggleSidebar">
      {{ isCollapsed ? '展开' : '折叠' }}
    </button>
    <div v-for="item in config" :key="item.name" class="sidebar-item" @click="loadPage(item.url)">
      <img :src="item.imageUrl" alt="封面图片" />
      <p>{{ item.name }}</p>
    </div>
  </div>
</template>

<script>
import config from '../config.js';

export default {
  data() {
    return {
      config,
      isCollapsed: false,
    };
  },
  methods: {
    toggleSidebar() {
      this.isCollapsed = !this.isCollapsed;
      this.$emit('sidebar-toggle', this.isCollapsed); // 触发自定义事件，传递折叠状态
    },
    loadPage(url) {
      this.$emit('load-page', url);
    },
  },
};
</script>