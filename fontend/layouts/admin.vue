<script setup lang="ts">
import Sidebar from '~/components/admins/Sidebar.vue';
import Topbar from '~/components/admins/Topbar.vue';

</script>

<template>
    <div class="bg-slate-200/60">
        <div class="flex h-screen">
            <Sidebar />
            <div class="flex-1 flex flex-col">
                <Topbar/> 
                <main class="flex-1 p-4">
                    <slot />
                </main>
            </div>
        </div>
    </div>
    
</template>