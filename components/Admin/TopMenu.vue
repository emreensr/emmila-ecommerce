<template>
    <div class=" border-b border-gray-300 shadow-md p-4 flex justify-between items-center px-6 h-20">
        <div>
            test
        </div>
        <div class="flex text-sm gap-3 text-end relative">
            <div>   
                <h2 class="font-bold">Mert Tekin</h2>
                <h2 class="font-light text-xs text-gray-500">Admin</h2>
            </div>
            <div @click="showMenu" class="w-10 h-10 cursor-pointer">
                <img class="rounded-full" src="https://react-material.fusetheme.com/assets/images/avatars/brian-hughes.jpg" alt="">
            </div>
            <div v-if="isShowMenu" class="absolute w-[200px] right-2 top-[43px] bg-white rounded-lg shadow-lg">
                <ul class="w-full py-1.5 text-start cursor-pointer">
                    <li class=" py-3 px-2 flex space-x-2 items-center">
                        <Icon name="ph:user" size="20"/>
                        <h2 class="font-semibold text-sm hover:border-b hover:border-gray-200 hover:scale-105">Profile</h2>
                    </li>
                    <li class=" py-3 px-2 flex space-x-2 items-center">
                        <Icon name="ic:outline-login" size="20"/>
                        <h2 class="font-semibold text-sm hover:border-b hover:border-gray-200 hover:scale-105">Log out</h2>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script setup>
    const isShowMenu = ref(false)
    function showMenu(){
        isShowMenu.value = !isShowMenu.value
    }
</script>


<style scoped>
    .w-custom{
        width: calc(100vh);
    }

</style>