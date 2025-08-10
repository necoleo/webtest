
<template>
  <div class="sidebar-container" >
    <div class="sidebar">
      <t-menu
          v-model:expanded="expanded"
          theme="light"
          default-value="1"
          expand-mutex
          :collapsed="collapsed"
      >
        <template #logo>
          <img
              height="28px"
              class="logo-img"
              src="@/assets/logo/logo.png"
              alt="Logo"
          />
        </template>
        <t-submenu value="functional-test">
          <template #icon>
            <t-icon name="check-rectangle" />
          </template>
          <template #title>
            <span>功能测试</span>
          </template>
          <t-menu-item value="functional-test-pm"> 项目管理 </t-menu-item>
          <t-menu-item value="functional-test-cases"> 测试用例 </t-menu-item>
        </t-submenu>
        <t-submenu value="api-test">
          <template #icon>
            <t-icon name="api" />
          </template>
          <template #title>
            <span>接口测试</span>
          </template>
          <t-menu-item value="api-test-interface-documentation"> 接口文档 </t-menu-item>
          <t-menu-item value="api-test-cases"> 接口测试用例 </t-menu-item>
          <t-menu-item value="api-test-reports"> 接口测试报告 </t-menu-item>
        </t-submenu>
        <t-submenu value="web-auto-test">
          <template #icon>
            <t-icon name="logo-chrome" />
          </template>
          <template #title>
            <span> web 自动化测试</span>
          </template>
          <t-menu-item value="web-auto-test-cases"> 自动化用例管理 </t-menu-item>
          <t-menu-item value="web-auto-test-scripts"> 脚本库 </t-menu-item>
          <t-menu-item value="web-auto-test-plans"> 执行计划 </t-menu-item>
          <t-menu-item value="web-auto-test-reports"> 自动化测试报告 </t-menu-item>
        </t-submenu>
        <t-submenu value="app-auto-test">
          <template #icon>
            <t-icon name="application" />
          </template>
          <template #title>
            <span> APP 自动化测试</span>
          </template>
          <t-menu-item value="app-auto-test-equipment-pool"> 设备池管理 </t-menu-item>
          <t-menu-item value="app-auto-test-config"> 自动化环境配置 </t-menu-item>
          <t-menu-item value="app-auto-test-cases"> App 自动化用例 </t-menu-item>
          <t-menu-item value="app-auto-test-log"> 执行日志 </t-menu-item>
          <t-menu-item value="app-auto-test-reports"> App 测试报告 </t-menu-item>
        </t-submenu>
        <t-submenu value="project-config">
          <template #icon>
            <t-icon name="dashboard"/>
          </template>
          <template #title>
            项目配置
          </template>
          <t-menu-item value="project-config-info"> 项目信息设置 </t-menu-item>
          <t-menu-item value="project-config-permissions"> 权限设置 </t-menu-item>
          <t-menu-item value="project-config-plans"> 流程配置 </t-menu-item>
          <t-menu-item value="project-config-SOC"> 系统集成配置 </t-menu-item>
        </t-submenu>
        <template #operations>
          <t-button variant="text" shape="square" @click="changeCollapsed">
            <template #icon><t-icon name="view-list" /></template>
          </t-button>
        </template>
      </t-menu>
    </div>
  </div>
</template>

<script setup lang="ts">
import {ref} from "vue";

const collapsed = ref(false);
const changeCollapsed = () => {
  collapsed.value = !collapsed.value;
};

// 初始展开
const expanded = ref(['functional-test']);
</script>


<style scoped>
  .sidebar-container {
    height: 100vh;
  }
</style>