
<template>
  <div class="container">
    <t-layout class="home-container">
      <t-aside>
        <div class="sidebar-content">
          <!-- 引入侧边栏 -->
          <Sidebar />
        </div>
      </t-aside>
      <t-layout>
        <t-content>
          <div class="main-content">
            <!--  -->
          </div>
        </t-content>
        <div class="footer-content">
          <t-footer> Heypon AI 测试</t-footer>
        </div>
      </t-layout>
    </t-layout>



  </div>
</template>

<script setup lang="ts">
  import Sidebar from "@/components/Sidebar.vue";
</script>

<style scoped>
  .home-container {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    height: 100vh;
    min-height: 796px;
    background: linear-gradient(135deg, #7db2c5 0%, #62bfd4 100%);
    background-repeat: no-repeat;
    background-size: cover;
    overflow: hidden;
  }
</style>