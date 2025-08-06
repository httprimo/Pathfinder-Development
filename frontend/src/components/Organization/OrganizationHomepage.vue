
<template>
  <div class="organization-homepage">
    <!-- Sidebar -->
    <transition name="slide">
      <aside class="sidebar" :class="{ collapsed: !isSidebarOpen }" @mouseenter="isSidebarOpen = true"
        @mouseleave="isSidebarOpen = false">
        <div class="icon" @click="$router.push('/OrganizationHomePage')">
          <svg width="30" height="30" viewBox="0 0 30 30" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M6.25 17.0585C6.25 16.0494 6.25 15.5448 6.47166 15.1141C6.69333 14.6833 7.1039 14.3901 7.92505 13.8035L13.8375 9.58034C14.3989 9.17938 14.6795 8.9789 15 8.9789C15.3205 8.9789 15.6011 9.17938 16.1625 9.58034L22.075 13.8035C22.8961 14.3901 23.3067 14.6833 23.5283 15.1141C23.75 15.5448 23.75 16.0494 23.75 17.0585V24.25C23.75 25.1928 23.75 25.6642 23.4571 25.9571C23.1642 26.25 22.6928 26.25 21.75 26.25H8.25C7.30719 26.25 6.83579 26.25 6.54289 25.9571C6.25 25.6642 6.25 25.1928 6.25 24.25V17.0585Z"
              fill="white" />
            <path
              d="M3.75 15.6366C3.75 15.9035 3.75 16.0369 3.8341 16.0781C3.91819 16.1192 4.02352 16.0373 4.23418 15.8734L13.7721 8.45502C14.362 7.99625 14.6569 7.76686 15 7.76686C15.3431 7.76686 15.638 7.99625 16.2279 8.45502L25.7658 15.8734C25.9765 16.0373 26.0818 16.1192 26.1659 16.0781C26.25 16.0369 26.25 15.9035 26.25 15.6366V14.7282C26.25 14.2478 26.25 14.0076 26.1483 13.7997C26.0466 13.5918 25.857 13.4444 25.4779 13.1495L16.2279 5.95502C15.638 5.49625 15.3431 5.26686 15 5.26686C14.6569 5.26686 14.362 5.49625 13.7721 5.95502L4.52212 13.1495C4.14295 13.4444 3.95337 13.5918 3.85168 13.7997C3.75 14.0076 3.75 14.2478 3.75 14.7282V15.6366Z"
              fill="white" />
            <path
              d="M16.125 18.75H13.875C12.7704 18.75 11.875 19.6454 11.875 20.75V26.1C11.875 26.1828 11.9422 26.25 12.025 26.25H17.975C18.0578 26.25 18.125 26.1828 18.125 26.1V20.75C18.125 19.6454 17.2296 18.75 16.125 18.75Z"
              fill="white" />
            <rect x="20" y="6.25" width="2.5" height="5" rx="0.5" fill="white" />
          </svg>
          <span>Home</span>
        </div>
        <div class="icon" @click="$router.push('/trainings')">
          <svg width="29" height="29" viewBox="0 0 29 29" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M20.5837 3.625C23.4119 3.625 24.8261 3.62526 25.7048 4.50391C26.5833 5.3826 26.5837 6.79675 26.5837 9.625V19.375C26.5837 22.2033 26.5833 23.6174 25.7048 24.4961C24.8261 25.3747 23.4119 25.375 20.5837 25.375H8.41666C5.58824 25.375 4.17425 25.3748 3.29557 24.4961C2.41689 23.6174 2.41666 22.2034 2.41666 19.375V9.625C2.41666 6.79657 2.41689 5.38259 3.29557 4.50391C4.17425 3.62523 5.58824 3.625 8.41666 3.625H20.5837ZM9.66666 12.292C9.11438 12.292 8.66666 12.7397 8.66666 13.292V20.542L8.67155 20.6445C8.72303 21.1485 9.1491 21.542 9.66666 21.542C10.1842 21.542 10.6103 21.1485 10.6618 20.6445L10.6667 20.542V13.292C10.6667 12.7397 10.2189 12.292 9.66666 12.292ZM19.3337 9.875C18.7814 9.875 18.3337 10.3227 18.3337 10.875V20.542L18.3385 20.6436C18.3896 21.148 18.8158 21.542 19.3337 21.542C19.8514 21.5418 20.2778 21.1479 20.3288 20.6436L20.3337 20.542V10.875C20.3337 10.3228 19.8858 9.87518 19.3337 9.875ZM14.4997 14.708C13.9476 14.7082 13.4998 15.156 13.4997 15.708V20.541L13.5046 20.6436C13.5557 21.1477 13.982 21.5408 14.4997 21.541C15.0175 21.541 15.4436 21.1478 15.4948 20.6436L15.4997 20.541V15.708C15.4995 15.1559 15.0518 14.708 14.4997 14.708Z"
              fill="white" />
          </svg>
          <span>Trainings</span>
        </div>
        <div class="icon" @click="togglePostOptions">
          <svg width="29" height="29" viewBox="0 0 29 29" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M3.625 7.625C3.625 5.41586 5.41586 3.625 7.625 3.625H21.375C23.5841 3.625 25.375 5.41586 25.375 7.625V21.375C25.375 23.5841 23.5841 25.375 21.375 25.375H7.625C5.41586 25.375 3.625 23.5841 3.625 21.375V7.625Z"
              stroke="white" stroke-width="2" />
            <path d="M14.5 9.6665L14.5 19.3332" stroke="white" stroke-width="2" stroke-linecap="square"
              stroke-linejoin="round" />
            <path d="M19.3333 14.5L9.66666 14.5" stroke="white" stroke-width="2" stroke-linecap="square"
              stroke-linejoin="round" />
          </svg>
          <span>Post</span>
        </div>
        <transition name="fade">
          <div v-if="showPostOptions && isSidebarOpen" class="post-options">
            <button @click="$router.push('/post-career')">Post Career</button>
            <button @click="$router.push('/post-training')">Post Training</button>
          </div>
        </transition>
        <div class="icon" @click="$router.push('/career')">
          <svg width="25" height="25" viewBox="0 0 25 25" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path
              d="M22.8798 11.0484C23.4046 10.8642 23.9845 11.1431 24.1081 11.6855C24.4792 13.3134 24.4217 15.0018 23.9268 16.6191C23.4739 18.0989 22.6698 19.4685 21.5787 20.6449C21.2148 21.0372 20.6017 21.0197 20.2239 20.6408L14.9487 15.3495C14.4292 14.8284 14.6314 13.9436 15.3257 13.6999L22.8798 11.0484ZM13 4.0826C13 3.50231 13.4932 3.04057 14.0672 3.12592C15.8633 3.39302 17.5788 4.00579 19.085 4.93161C20.3794 5.72731 21.4793 6.72976 22.3343 7.87824C22.709 8.38157 22.4513 9.07932 21.8592 9.28718L14.3313 11.9301C13.6809 12.1584 13 11.6758 13 10.9865V4.0826Z"
              fill="white" />
            <path
              d="M11.9511 13.2908C11.9512 13.5763 12.0581 13.8518 12.25 14.0632L19.2677 21.7886C19.6714 22.233 19.5963 22.9337 19.0759 23.2331C18.245 23.7112 17.354 24.0924 16.4209 24.365C14.5402 24.9144 12.5476 25.0087 10.6201 24.6394C8.69236 24.2701 6.88846 23.4478 5.36911 22.2468C3.84993 21.0459 2.66126 19.5025 1.90915 17.7537C1.15711 16.0048 0.864996 14.1043 1.05759 12.2205C1.25024 10.3365 1.92171 8.52693 3.01364 6.95288C4.1056 5.37884 5.58398 4.08845 7.31735 3.19605C8.43484 2.62073 9.63633 2.22318 10.8757 2.01305C11.4515 1.91541 11.9511 2.37876 11.9511 2.96284V13.2908Z"
              fill="white" />
          </svg>
          <span>Career</span>
        </div>
        <div class="icon" @click="$router.push('/profile')">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M15.6001 9.6C15.6001 11.5882 13.9884 13.2 12.0001 13.2C10.0119 13.2 8.40015 11.5882 8.40015 9.6C8.40015 7.61177 10.0119 6 12.0001 6C13.9884 6 15.6001 7.61177 15.6001 9.6ZM14.4001 9.6C14.4001 10.9255 13.3256 12 12.0001 12C10.6747 12 9.60015 10.9255 9.60015 9.6C9.60015 8.27452 10.6747 7.2 12.0001 7.2C13.3256 7.2 14.4001 8.27452 14.4001 9.6Z"
              fill="white" />
            <path
              d="M12.0001 15C8.11552 15 4.80571 17.297 3.54492 20.5152C3.85206 20.8202 4.1756 21.1087 4.51412 21.3792C5.45296 18.4246 8.39818 16.2 12.0001 16.2C15.6021 16.2 18.5473 18.4246 19.4862 21.3792C19.8247 21.1087 20.1482 20.8202 20.4554 20.5152C19.1946 17.2971 15.8848 15 12.0001 15Z"
              fill="white" />
          </svg>
          <span>Profile</span>
        </div>
      </aside>
    </transition na>

    <!-- Main content -->
    <main class="content">
      <header class="topbar">
        <div class="search-wrapper">
          <span class="logo-text">Pathfinder</span>
          <div class="search-container">
            <span class="search-icon"><svg width="48" height="49" viewBox="0 0 48 49" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <g clip-path="url(#clip0_790_1119)">
                  <path
                    d="M31.6 33.5L25.3 27.2C24.8 27.6 24.225 27.9167 23.575 28.15C22.925 28.3833 22.2333 28.5 21.5 28.5C19.6833 28.5 18.1458 27.8708 16.8875 26.6125C15.6292 25.3542 15 23.8167 15 22C15 20.1833 15.6292 18.6458 16.8875 17.3875C18.1458 16.1292 19.6833 15.5 21.5 15.5C23.3167 15.5 24.8542 16.1292 26.1125 17.3875C27.3708 18.6458 28 20.1833 28 22C28 22.7333 27.8833 23.425 27.65 24.075C27.4167 24.725 27.1 25.3 26.7 25.8L33 32.1L31.6 33.5ZM21.5 26.5C22.75 26.5 23.8125 26.0625 24.6875 25.1875C25.5625 24.3125 26 23.25 26 22C26 20.75 25.5625 19.6875 24.6875 18.8125C23.8125 17.9375 22.75 17.5 21.5 17.5C20.25 17.5 19.1875 17.9375 18.3125 18.8125C17.4375 19.6875 17 20.75 17 22C17 23.25 17.4375 24.3125 18.3125 25.1875C19.1875 26.0625 20.25 26.5 21.5 26.5Z"
                    fill="#44576D" />
                </g>
                <defs>
                  <clipPath id="clip0_790_1119">
                    <rect x="4" y="4.5" width="40" height="40" rx="20" fill="white" />
                  </clipPath>
                </defs>
              </svg>
            </span>
            <input type="text" placeholder="Search..." class="search-input" />
          </div>
        </div>
        <button class="search-btn">Search</button>
      </header>

      <!-- Chart Section -->
      <section class="chart-section">
        <canvas id="applicantChart"></canvas>
        <div class="legend">
          <span><span class="dot blue"></span> Training Applicants</span>
          <span><span class="dot purple"></span> Job Applicants</span>
        </div>
      </section>

      <!-- Trainings Section -->
      <section class="section-block">
        <h2>Trainings</h2>
        <div class="card-grid">
          <div class="info-card">
            <p>Professional development in emerging technologies and cognitive enhancement</p>
            <div class="card-footer">
              <img src="https://placehold.co/30x30" alt="Logo" />
              <div class="actions">
                <button class="bookmark"><svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                      d="M17.204 10.796L19 9C19.5453 8.45475 19.8179 8.18213 19.9636 7.88803C20.2409 7.32848 20.2409 6.67152 19.9636 6.11197C19.8179 5.81788 19.5453 5.54525 19 5C18.4548 4.45475 18.1821 4.18213 17.888 4.03639C17.3285 3.75911 16.6715 3.75911 16.112 4.03639C15.8179 4.18213 15.5453 4.45475 15 5L13.1814 6.81866C14.1452 8.46926 15.5314 9.84482 17.204 10.796ZM11.7269 8.27311L4.8564 15.1436C4.43134 15.5687 4.21881 15.7812 4.07907 16.0423C3.93934 16.3034 3.88039 16.5981 3.7625 17.1876L3.1471 20.2646C3.08058 20.5972 3.04732 20.7635 3.14193 20.8581C3.23654 20.9527 3.40284 20.9194 3.73545 20.8529L6.81243 20.2375C7.40189 20.1196 7.69661 20.0607 7.95771 19.9209C8.21881 19.7812 8.43134 19.5687 8.8564 19.1436L15.7458 12.2542C14.1241 11.2386 12.7524 9.87627 11.7269 8.27311Z"
                      fill="white" />
                  </svg>
                </button>
                <button class="applicants-btn">Applicants</button>
              </div>
            </div>
          </div>
          <div class="info-card">
            <p>Mind Over Machine: Navigating AI in Everyday Life</p>
            <div class="card-footer">
              <img src="https://placehold.co/30x30" alt="Logo" />
              <div class="actions">
                <button class="bookmark"><svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                      d="M17.204 10.796L19 9C19.5453 8.45475 19.8179 8.18213 19.9636 7.88803C20.2409 7.32848 20.2409 6.67152 19.9636 6.11197C19.8179 5.81788 19.5453 5.54525 19 5C18.4548 4.45475 18.1821 4.18213 17.888 4.03639C17.3285 3.75911 16.6715 3.75911 16.112 4.03639C15.8179 4.18213 15.5453 4.45475 15 5L13.1814 6.81866C14.1452 8.46926 15.5314 9.84482 17.204 10.796ZM11.7269 8.27311L4.8564 15.1436C4.43134 15.5687 4.21881 15.7812 4.07907 16.0423C3.93934 16.3034 3.88039 16.5981 3.7625 17.1876L3.1471 20.2646C3.08058 20.5972 3.04732 20.7635 3.14193 20.8581C3.23654 20.9527 3.40284 20.9194 3.73545 20.8529L6.81243 20.2375C7.40189 20.1196 7.69661 20.0607 7.95771 19.9209C8.21881 19.7812 8.43134 19.5687 8.8564 19.1436L15.7458 12.2542C14.1241 11.2386 12.7524 9.87627 11.7269 8.27311Z"
                      fill="white" />
                  </svg>
                </button>
                <button class="applicants-btn">Applicants</button>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Career Section -->
      <section class="section-block">
        <h2>Career Opportunities</h2>
        <div class="card-grid">
          <div class="info-card">
            <p>Hiring: Front-End Developer! If you speak fluent React, we want you!</p>
            <div class="card-footer">
              <img src="https://placehold.co/30x30" alt="Logo" />
              <div class="actions">
                <button class="bookmark"><svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                      d="M17.204 10.796L19 9C19.5453 8.45475 19.8179 8.18213 19.9636 7.88803C20.2409 7.32848 20.2409 6.67152 19.9636 6.11197C19.8179 5.81788 19.5453 5.54525 19 5C18.4548 4.45475 18.1821 4.18213 17.888 4.03639C17.3285 3.75911 16.6715 3.75911 16.112 4.03639C15.8179 4.18213 15.5453 4.45475 15 5L13.1814 6.81866C14.1452 8.46926 15.5314 9.84482 17.204 10.796ZM11.7269 8.27311L4.8564 15.1436C4.43134 15.5687 4.21881 15.7812 4.07907 16.0423C3.93934 16.3034 3.88039 16.5981 3.7625 17.1876L3.1471 20.2646C3.08058 20.5972 3.04732 20.7635 3.14193 20.8581C3.23654 20.9527 3.40284 20.9194 3.73545 20.8529L6.81243 20.2375C7.40189 20.1196 7.69661 20.0607 7.95771 19.9209C8.21881 19.7812 8.43134 19.5687 8.8564 19.1436L15.7458 12.2542C14.1241 11.2386 12.7524 9.87627 11.7269 8.27311Z"
                      fill="white" />
                  </svg>
                </button>
                <button class="applicants-btn">Applicants</button>
              </div>
            </div>
          </div>
          <div class="info-card">
            <p>Chef Wanted! Join a fast-paced kitchen with a passion for food!</p>
            <div class="card-footer">
              <img src="https://placehold.co/30x30" alt="Logo" />
              <div class="actions">
                <button class="bookmark"><svg width="24" height="24" viewBox="0 0 24 24" fill="none"
                    xmlns="http://www.w3.org/2000/svg">
                    <path fill-rule="evenodd" clip-rule="evenodd"
                      d="M17.204 10.796L19 9C19.5453 8.45475 19.8179 8.18213 19.9636 7.88803C20.2409 7.32848 20.2409 6.67152 19.9636 6.11197C19.8179 5.81788 19.5453 5.54525 19 5C18.4548 4.45475 18.1821 4.18213 17.888 4.03639C17.3285 3.75911 16.6715 3.75911 16.112 4.03639C15.8179 4.18213 15.5453 4.45475 15 5L13.1814 6.81866C14.1452 8.46926 15.5314 9.84482 17.204 10.796ZM11.7269 8.27311L4.8564 15.1436C4.43134 15.5687 4.21881 15.7812 4.07907 16.0423C3.93934 16.3034 3.88039 16.5981 3.7625 17.1876L3.1471 20.2646C3.08058 20.5972 3.04732 20.7635 3.14193 20.8581C3.23654 20.9527 3.40284 20.9194 3.73545 20.8529L6.81243 20.2375C7.40189 20.1196 7.69661 20.0607 7.95771 19.9209C8.21881 19.7812 8.43134 19.5687 8.8564 19.1436L15.7458 12.2542C14.1241 11.2386 12.7524 9.87627 11.7269 8.27311Z"
                      fill="white" />
                  </svg>
                </button>
                <button class="applicants-btn">Applicants</button>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { onMounted } from 'vue'
import Chart from 'chart.js/auto'

const showPostOptions = ref(false)

const togglePostOptions = () => {
  showPostOptions.value = !showPostOptions.value
}

const isSidebarOpen = ref(false)

const toggleSidebar = () => {
  isSidebarOpen.value = !isSidebarOpen.value
}

onMounted(() => {
  const ctx = document.getElementById('applicantChart')
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['January', 'February', 'March', 'April', 'May', 'June'],
      datasets: [
        {
          label: 'Training Applicants',
          data: [10, 20, 15, 25, 40, 30],
          borderColor: '#3182ce',
          fill: false,
          tension: 0.4
        },
        {
          label: 'Job Applicants',
          data: [5, 15, 20, 22, 50, 35],
          borderColor: '#9f7aea',
          fill: false,
          tension: 0.4
        }
      ]
    },
    options: {
      responsive: true,
      plugins: {
        legend: { display: false }
      }
    }
  })
})
</script>

<style scoped>
.post-icon {
  position: relative;
  width: 100%;
}

.post-options {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 8px;
  background-color: #2d3748;
  padding: 10px;
  border-radius: 8px;
  z-index: 100;
  white-space: nowrap;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  transition: opacity 0.2s ease;
}

.post-options button {
  background-color: #44576D;
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
  width: 200px;
  /* Expanded width */
  background-color: #44576D;
  color: white;
  display: flex;
  flex-direction: column;
  align-items: start;
  padding: 20px 10px;
  transition: width 0.3s ease;
  overflow: hidden;
}

.sidebar.collapsed {
  width: 60px;
  /* Collapsed width */
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
  transition: background-color 0.2s ease;
}

.sidebar .icon svg {
  flex-shrink: 0;
  /* Ensures icon doesn't shrink */
  width: 30px;
  height: 30px;
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
  /* Keep it centered */
  align-items: center;
  margin-bottom: 40px;
}

.logo-title {
  font-size: 32px;
  font-weight: 700;
  color: #2d3748;
}

.logo-text {
  font-size: 26px;
  font-weight: 700;
  color: #44576D;
  font-family: 'Segoe UI', sans-serif;
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
  display: flex;
  align-items: center;
  justify-content: center;
  pointer-events: none;
}

.search-input {
  width: 100%;
  padding: 10px 16px 10px 56px;
  /* <-- add more left padding here */
  border: 1px solid #ccc;
  border-radius: 24px;
  font-size: 14px;
  background-color: #f7fafc;
  color: #000;
  transition: border-color 0.2s ease;
}

.search-input:focus {
  outline: none;
  border-color: #3182ce;
}

.search-wrapper {
  display: flex;
  align-items: center;
  gap: 16px;
  /* space between "Pathfinder" and search bar */
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

.chart-section {
  background: white;
  padding: 30px;
  border-radius: 16px;
  margin: 40px auto;
  width: 90%;
  max-width: 900px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.chart-section canvas {
  width: 100% !important;
  max-width: 800px;
  height: auto !important;
  margin: 0 auto;
}

.legend {
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-top: 10px;
  font-size: 14px;
  color: #4a5568;
}

.dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  margin-right: 6px;
}

.dot.blue {
  background-color: #3182ce;
}

.dot.purple {
  background-color: #9f7aea;
}

.section-block {
  margin: 50px auto;
  max-width: 1000px;
  padding: 0 20px;
  text-align: center;
}

.section-block h2 {
  font-size: 26px;
  color: #2d3748;
  margin-bottom: 20px;
  text-align: center;
}

.card-grid {
  display: flex;
  justify-content: center;
  /* center the grid */
  flex-wrap: wrap;
  gap: 16px;
}

.info-card {
  background: white;
  padding: 20px;
  border-radius: 12px;
  flex: 1 1 300px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.info-card p {
  font-size: 15px;
  color: #2d3748;
  margin-bottom: 16px;
}

.card-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.card-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  /* logo on left, buttons on right */
}

.card-footer .actions {
  display: flex;
  gap: 8px;
  /* adjust spacing between buttons */
}

.bookmark,
.applicants-btn {
  background-color: #44576D;
  color: white;
  border: none;
  padding: 6px 12px;
  border-radius: 6px;
  font-size: 14px;
  cursor: pointer;
}

.applicants-btn {
  background-color: #44576D;
}

.applicants-btn:hover {
  background-color: #5a667d;
}

.search-btn {
  background-color: #44576D;
  color: white;
  padding: 8px 20px;
  border: none;
  border-radius: 20px;
  margin-left: 20px;
  font-size: 14px;
  cursor: pointer;
  font-weight: 600;
}

.search-btn:hover {
  background-color: #5a667d;
}
</style>
