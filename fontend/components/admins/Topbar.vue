
<template>
    <div id="admin-topbar" class="flex justify-between items-center border-b border-gray-300 ">
        <div class="flex pl-3">
            <FontAwesomeIcon :icon="['fas', 'search']" class="pt-1" />
            <input type="text" placeholder="Search here"
                class="px-3 border-b border-gray-200 focus:outline-none">
        </div>

        <div class="flex items-center space-x-3">
            <FontAwesomeIcon :icon="['fas', 'message']" class="icon" />
            <FontAwesomeIcon :icon="['fas', 'message']" class="icon" />
        </div>
    </div>
</template>