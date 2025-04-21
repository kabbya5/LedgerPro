<template>
    <div class="flex" id="admin-sidebar">
        <!-- Sidebar -->
        <aside>
            <!-- Logo  -->
            <div class="flex justify-center items-center border-b border-gray-300 dark:border-gray-700 py-3">
                <img src="https://stackbros.in/darkone/assets/images/logo-dark.png" class="w-6 h-6" alt="Logo" />
                <span class="font-bold text-lg">Darkone</span>
            </div>
    
            <!-- Menu -->
            <div class="text-xs px-3 py-2 uppercase text-gray-400 dark:text-gray-500">
                Menu...
            </div>

            <nav class="space-y-2 px-3 py-2">
                <NuxtLink to="/admin/dashboard" class="sidebar-link">
                    <div class="flex justify-between items-center">
                        <span class="flex items-center space-x-2">
                            <i class="fas fa-home"></i>
                            <span>Dashboard</span>
                        </span>
                        <span class="text-xs bg-purple-600 text-white rounded-full px-2 py-0.5">03</span>
                    </div>
                </NuxtLink>

                <div class="sidebar-section">
                    <div v-for="link in navLinks" :key="link.name">
                        <div class="menu mt-2 flex justify-between items-center" 
                            @click="toggleDropdown(link.name)">
                            <NuxtLink to="/" class="menu-item flex items-center w-full justify-between">
                              <span class=" space-x-3 py-1 ">
                                <FontAwesomeIcon :icon="link.icon" class="menu-item-icon" />
                                <span> {{ link.name }}</span>
                              </span>
                              <FontAwesomeIcon :icon="open[link.name] ? ['fas', 'chevron-up'] : ['fas', 'chevron-down']" />
                            </NuxtLink>
                            
                            
                        </div>
                        <div v-if="open[link.name]" class="ml-2 space-y-1 flex flex-col">
                            <NuxtLink to="/auth/signin" class="sidebar-sublink my-2 py-1 rounded-md px-4 bg-gray-200/60">Sign In</NuxtLink>
                            <NuxtLink to="/auth/signup" class="sidebar-sublink">Sign Up</NuxtLink>
                            <NuxtLink to="/auth/reset-password" class="sidebar-sublink">Reset Password</NuxtLink>
                            <NuxtLink to="/auth/lock-screen" class="sidebar-sublink">Lock Screen</NuxtLink>
                        </div>
                    </div>
                </div>


                <div class="text-xs uppercase text-gray-400 dark:text-gray-500 pt-4">UI Kit...</div>

                <div class="sidebar-section" v-for="section in uiSections" :key="section.name">
                    <div class="sidebar-dropdown" @click="toggleDropdown(section.name)">
                        <span class="flex items-center space-x-2">
                            <i :class="section.icon"></i>
                            <span>{{ section.title }}</span>
                        </span>
                        <i :class="['fas', open[section.name] ? 'fa-chevron-up' : 'fa-chevron-down']"></i>
                    </div>
                    <div v-if="open[section.name]" class="ml-6 space-y-1">
                        <NuxtLink v-for="link in section.links" :key="link.title" :to="link.route" class="sidebar-sublink">
                            {{ link.title }}
                        </NuxtLink>
                    </div>
                </div>
            </nav>
        </aside>
    </div>
</template>
  
  <script setup lang="ts">
import { Title } from '#components';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

  
  const showSidebar = ref(false)
  const open = ref({
    auth: false,
    baseui: false,
    forms: false,
    charts: false,
    tables: false,
    icons: false
  })

  const navLinks = [
    {
        name:'Ecommerce',
        title:'Ecommerce',
        icon:['fas','house'],
        url:'/fa/user',
    }
  ];
  
  const uiSections = [
    {
      name: 'baseui',
      title: 'Base UI',
      icon: 'fas fa-leaf',
      links: [
        { title: 'Buttons', route: '/ui/buttons' },
        { title: 'Cards', route: '/ui/cards' }
      ]
    },
    {
      name: 'charts',
      title: 'Apex Charts',
      icon: 'fas fa-chart-bar',
      links: [
        { title: 'Line Chart', route: '/charts/line' }
      ]
    },
    {
      name: 'forms',
      title: 'Forms',
      icon: 'fas fa-lock',
      links: [
        { title: 'Form Elements', route: '/forms/elements' }
      ]
    },
    {
      name: 'tables',
      title: 'Tables',
      icon: 'fas fa-table',
      links: [
        { title: 'Basic Table', route: '/tables/basic' }
      ]
    },
    {
      name: 'icons',
      title: 'Icons',
      icon: 'fas fa-globe',
      links: [
        { title: 'Font Awesome', route: '/icons/fontawesome' }
      ]
    }
  ]
  
  const toggleSidebar = () => {
    showSidebar.value = !showSidebar.value
  }
  
  const toggleDropdown = (section) => {
    open.value[section] = !open.value[section]
  }
</script>
  

  