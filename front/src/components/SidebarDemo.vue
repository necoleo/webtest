<template>
  <div class="sidebar-container">
    <!-- 背景装饰 -->
    <div class="background-decoration">
      <div class="circle circle-1"></div>
      <div class="circle circle-2"></div>
    </div>

    <!-- 侧边栏内容 -->
    <div class="sidebar-content">
      <!-- Logo区域 -->
      <div class="logo-section">
        <div class="logo-container">
          <img
            class="logo-img"
            src="@/assets/logo/logo.png"
            alt="Logo"
          />
          <h2 class="app-title">WebTest</h2>
        </div>
      </div>

      <!-- 导航菜单 -->
      <nav class="navigation-menu">
        <div class="menu-section">
          <h3 class="menu-title">主要功能</h3>
          <ul class="menu-list">
            <li class="menu-item active">
              <t-icon name="home" class="menu-icon" />
              <span class="menu-text">首页</span>
            </li>
            <li class="menu-item">
              <t-icon name="user" class="menu-icon" />
              <span class="menu-text">用户管理</span>
            </li>
            <li class="menu-item">
              <t-icon name="setting" class="menu-icon" />
              <span class="menu-text">系统设置</span>
            </li>
            <li class="menu-item">
              <t-icon name="chart" class="menu-icon" />
              <span class="menu-text">数据统计</span>
            </li>
          </ul>
        </div>

        <div class="menu-section">
          <h3 class="menu-title">工具</h3>
          <ul class="menu-list">
            <li class="menu-item">
              <t-icon name="file" class="menu-icon" />
              <span class="menu-text">文件管理</span>
            </li>
            <li class="menu-item">
              <t-icon name="help-circle" class="menu-icon" />
              <span class="menu-text">帮助中心</span>
            </li>
          </ul>
        </div>
      </nav>

      <!-- 用户信息 -->
      <div class="user-section">
        <div class="user-info">
          <div class="user-avatar">
            <t-icon name="user-circle" />
          </div>
          <div class="user-details">
            <h4 class="user-name">管理员</h4>
            <p class="user-role">超级管理员</p>
          </div>
        </div>
        <t-button
          class="logout-button"
          theme="default"
          variant="outline"
          size="small"
          @click="handleLogout"
        >
          <t-icon name="logout" />
          退出登录
        </t-button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { MessagePlugin } from 'tdesign-vue-next';
import { useRouter } from 'vue-router';

const router = useRouter();

const handleLogout = () => {
  MessagePlugin.success('退出登录成功');
  router.push({ name: 'Login' });
};
</script>

<style scoped>
.sidebar-container {
  position: relative;
  width: 280px;
  height: 100vh;
  background: linear-gradient(135deg, #7db2c5 0%, #62bfd4 100%);
  background-repeat: no-repeat;
  background-size: cover;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}

.background-decoration {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
  z-index: 0;
}

.circle {
  position: absolute;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
}

.circle-1 {
  width: 120px;
  height: 120px;
  top: 15%;
  right: 20%;
  animation: float 8s ease-in-out infinite;
}

.circle-2 {
  width: 80px;
  height: 80px;
  bottom: 25%;
  left: 15%;
  animation: float 6s ease-in-out infinite reverse;
}

@keyframes float {
  0%, 100% { transform: translateY(0px); }
  50% { transform: translateY(-15px); }
}

.sidebar-content {
  position: relative;
  z-index: 1;
  display: flex;
  flex-direction: column;
  height: 100%;
  padding: 20px;
}

/* Logo区域 */
.logo-section {
  text-align: center;
  padding: 30px 0;
  margin-bottom: 30px;
}

.logo-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.logo-img {
  width: 80px;
  height: 80px;
  object-fit: contain;
  border-radius: 16px;
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  padding: 15px;
  margin-bottom: 15px;
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease;
}

.logo-img:hover {
  transform: scale(1.05);
}

.app-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  margin: 0;
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
}

/* 导航菜单 */
.navigation-menu {
  flex: 1;
  margin-bottom: 30px;
}

.menu-section {
  margin-bottom: 30px;
}

.menu-title {
  font-size: 0.9rem;
  font-weight: 600;
  color: rgba(255, 255, 255, 0.8);
  margin: 0 0 15px 0;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.menu-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu-item {
  display: flex;
  align-items: center;
  padding: 12px 16px;
  margin-bottom: 8px;
  border-radius: 12px;
  cursor: pointer;
  transition: all 0.3s ease;
  color: rgba(255, 255, 255, 0.9);
}

.menu-item:hover {
  background: rgba(255, 255, 255, 0.15);
  backdrop-filter: blur(10px);
  transform: translateX(5px);
}

.menu-item.active {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(15px);
  color: white;
  box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
}

.menu-icon {
  font-size: 1.2rem;
  margin-right: 12px;
  opacity: 0.9;
}

.menu-text {
  font-size: 0.95rem;
  font-weight: 500;
}

/* 用户信息 */
.user-section {
  padding: 20px;
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(15px);
  border-radius: 16px;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.user-info {
  display: flex;
  align-items: center;
  margin-bottom: 15px;
}

.user-avatar {
  width: 45px;
  height: 45px;
  border-radius: 50%;
  background: rgba(255, 255, 255, 0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 12px;
  font-size: 1.5rem;
  color: white;
}

.user-details {
  flex: 1;
}

.user-name {
  font-size: 1rem;
  font-weight: 600;
  color: white;
  margin: 0 0 4px 0;
}

.user-role {
  font-size: 0.85rem;
  color: rgba(255, 255, 255, 0.8);
  margin: 0;
}

.logout-button {
  width: 100%;
  border-radius: 10px;
  border: 1px solid rgba(255, 255, 255, 0.3);
  color: rgba(255, 255, 255, 0.9);
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  transition: all 0.3s ease;
}

.logout-button:hover {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.5);
  color: white;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .sidebar-container {
    width: 100%;
    height: auto;
    min-height: 100vh;
  }
  
  .sidebar-content {
    padding: 15px;
  }
  
  .logo-img {
    width: 60px;
    height: 60px;
  }
  
  .app-title {
    font-size: 1.2rem;
  }
}
</style>
