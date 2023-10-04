<template>
    <div class="flex h-screen">
        <div class="bg-[#191919] transform duration-200 ease-in-out overflow-y-auto flex flex-col" :class="isHiddenMenu ? 'w-16' : 'w-96'">
            <div @click="hideLeftMenu" class="h-20 w-full p-6 flex justify-between items-center text-white">
                <h2 v-if="!isHiddenMenu">Logo</h2>
                <div class="space-y-1">
                    <div class="w-4 h-0.5 bg-white rounded-3xl"></div>
                    <div class="w-4 h-0.5 bg-white rounded-3xl"></div>
                    <div class="w-4 h-0.5 bg-white rounded-3xl"></div>
                </div>
            </div>
            <div class="mt-1 w-full text-center text-md text-white flex flex-col items-center justify-center space-y-6">
                <img :class="isHiddenMenu ? 'w-8 h-8' : 'w-24 h-24' " class="rounded-full" src="https://react-material.fusetheme.com/assets/images/avatars/brian-hughes.jpg" alt="">
                <div>
                    <h2 v-if="!isHiddenMenu" class="font-bold text-sm">Mert Tekin</h2>
                    <h2 v-if="!isHiddenMenu" class="text-[#94a3b8] text-sm">tekin@kranas.com</h2>
                </div>
            </div>
            <div class="mt-10 w-full text-sm text-gray-300 flex flex-col items-center justify-center space-y-6 text-start">
                <ul class="w-full px-5 space-y-6">
                    <NuxtLink to="/panel/dashboard" class="flex items-center justify-start space-x-4">
                        <Icon name="carbon:dashboard-reference" size=20 />
                        <h1 v-if="!isHiddenMenu">Dashboard</h1>
                    </NuxtLink>
                    <NuxtLink to="/panel/ecommerce" class="flex items-center justify-start space-x-4">
                        <Icon name="tdesign:cart" size=20 />
                        <h1 v-if="!isHiddenMenu">E-commerce</h1>
                    </NuxtLink>
                </ul>
            </div>
            <div class="mt-auto pb-10 w-full text-sm text-gray-300 flex flex-col items-center justify-center space-y-6 text-start">
                <ul class="w-full px-5 space-y-6">
                    <li class="flex items-center justify-start space-x-4">
                        <Icon name="ic:outline-settings" size=20 />
                        <h1 v-if="!isHiddenMenu">Settings</h1>
                    </li>
                </ul>
            </div>
        </div>
        <div class="w-full">
            <AdminTopMenu/>
            <NuxtPage/>
        </div>
    </div>
</template>

<script setup>
    definePageMeta({
        layout:'adminLayout',
    })


    const isHiddenMenu = ref(false)
    function hideLeftMenu() {
        isHiddenMenu.value = !isHiddenMenu.value
        console.log('====================================');
        console.log(isHiddenMenu);
        console.log('====================================');
    }
</script>