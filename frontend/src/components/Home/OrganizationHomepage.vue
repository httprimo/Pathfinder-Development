
<template>
    <div class="organization-homepage">
    <!-- Sidebar -->
    <transition name="slide">
      <aside
          class="sidebar"
          :class="{ collapsed: !isSidebarOpen }"
           @mouseenter="isSidebarOpen = true"
           @mouseleave="isSidebarOpen = false"
        >
        <div class="icon" @click="$router.push('/home')">
          🏠<span>Home</span>
        </div>
        <div class="icon" @click="$router.push('/trainings')">
          📊<span>Trainings</span>
        </div>
        <div class="icon" @click="togglePostOptions">
          📨<span>Post</span>
        </div>
        <div v-if="showPostOptions" class="post-options">
          <button @click="$router.push('/post-career')">Post Career</button>
          <button @click="$router.push('/post-training')">Post Training</button>
        </div>
        <div class="icon" @click="$router.push('/career')">
          📈<span>Career</span>
        </div>
      </aside>
    </transition na>

    <!-- Main content -->
    <main class="content">
      <header class="topbar">
          <div class="search-container">
            <span class="search-icon">🔍</span>
          <input type="text" placeholder="Search..." class="search-input" />
           </div>
          </header>
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const showPostOptions = ref(false)

const togglePostOptions = () => {
  showPostOptions.value = !showPostOptions.value
}

const isSidebarOpen = ref(true)

const toggleSidebar = () => {
  isSidebarOpen.value = !isSidebarOpen.value
}


</script>


<style scoped>

.post-icon {
  position: relative;
  width: 100%;
}

.post-options {
  position:relative;
  display: flex;
  flex-direction: column;
  gap: 8px;
  background-color: #2d3748;
  padding: 10px;
  border-radius: 8px;
  z-index: 100;
  white-space: nowrap;
  box-shadow: 0 0 10px rgba(0,0,0,0.3);
  transition: opacity 0.2s ease;
}

.post-options button {
  background-color: #4a5568;
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 4px;
  cursor: pointer;
  text-align: left;
  font-size: 13px;
  width: 120px;
}

.post-options button:hover {
  background-color: #5a667d;
}

/* Optional fade animation */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.organization-homepage {
  display: flex;
  height: 100vh;
  font-family: 'Segoe UI', sans-serif;
  background-color: #f4f4f4;
}

/* Sidebar */
.sidebar {
  width: 200px; /* Expanded width */
  background-color: #2d3748;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: start;
  padding: 20px 10px;
  transition: width 0.3s ease;
  overflow: hidden;
}

.sidebar.collapsed {
  width: 60px; /* Collapsed width */
}

.sidebar .icon {
  display: flex;
  align-items: center;
  gap: 10px;
  margin: 20px 0;
  font-size: 16px;
  cursor: pointer;
  padding: 8px;
  border-radius: 8px;
  width: 100%;
  white-space: nowrap;
}

.sidebar .icon:hover {
  background-color: #4a5568;
}

.sidebar .icon span {
  transition: opacity 0.3s ease;
  opacity: 1;
}

.sidebar.collapsed .icon span {
  opacity: 0;
  pointer-events: none;
}


/* Main Content */
.content {
  flex: 1;
  padding: 30px 40px;
  overflow-y: auto;
}

.topbar {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 40px;
}

.logo-title {
  font-size: 32px;
  font-weight: 700;
  color: #2d3748;
}

.search-container {
  position: relative;
  width: 500px;
  max-width: 100%;
}

.search-icon {
  position: absolute;
  left: 12px;
  top: 50%;
  transform: translateY(-50%);
  color: #a0aec0;
  font-size: 16px;
}

.search-input {
  width: 100%;
  padding: 10px 16px 10px 40px; /* space for icon */
  border: 1px solid #ccc;
  border-radius: 24px;
  font-size: 14px;
  background-color: #f7fafc;
  color: #000; /* <-- this makes typed text black */
  transition: border-color 0.2s ease;
}

.search-input:focus {
  outline: none;
  border-color: #3182ce;
}

/* Post Card */
.post-card {
  background-color: white;
  padding: 24px;
  border-radius: 16px;
  max-width: 640px;
  margin: auto;
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.post-header {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 20px;
}

.avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  margin-right: 10px;
}

.poster-name {
  font-weight: 600;
  font-size: 16px;
}

.poster-image {
  width: 100%;
  max-height: 500px;
  object-fit: cover;
  border-radius: 12px;
  margin: 20px 0;
}

.description {
  font-size: 15px;
  color: #4a5568;
  margin-bottom: 24px;
}

.btn-row {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  justify-content: center;
}

.register-button {
  background-color: #3182ce;
  color: white;
  padding: 10px 24px;
  border-radius: 6px;
  border: none;
  cursor: pointer;
  font-weight: 600;
}

.register-button:hover {
  background-color: #2b6cb0;
}

.visit-link {
  display: inline-block;
  padding: 10px 24px;
  background-color: transparent;
  border: 2px solid #3182ce;
  color: #3182ce;
  border-radius: 6px;
  font-weight: 600;
  text-decoration: none;
}

.visit-link:hover {
  background-color: #e6f0fb;
}
</style>
