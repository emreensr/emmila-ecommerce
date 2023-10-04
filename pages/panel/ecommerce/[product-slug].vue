<template>
    <div class="bg-gray-50">
        <div class="flex items-center justify-between px-10 py-6">
            <div class="flex flex-col space-y-4">
                <div class="flex items-center justify-start space-x-2">
                    <Icon name="material-symbols:arrow-left-alt-rounded" size="16"/>
                    <span class="block text-start"> Products </span>
                </div>
                <div class="flex space-x-4 items-center justify-center">
                    <div class="bg-gray-200 w-10 h-12 items-center justify-center flex">
                        <img src="https://react-material.fusetheme.com/assets/images/apps/ecommerce/braies-lake.jpg" alt="">
                    </div>
                    <div>
                        <h2 class="font-bold text-3xl">Lorem ipsum dolor sit.</h2>
                        <h3 class="text-gray-300 text-md">Lorem, ipsum dolor.</h3>
                    </div>
                </div>
            </div>
            <div class="flex items-center justify-center space-x-4">
                <button class="flex justify-center items-center space-x-2 text-white bg-purple-500 bg-opacity-70 py-2 px-3 h-8 rounded-full shadow-md">
                    <Icon name="bi:trash" size="16"/>
                    <span>Remove</span>
                </button>
                <button class="h-8 py-2 px-3 flex justify-center items-center rounded-full bg-white shadow-md">
                    <span>
                        Save
                    </span>
                </button>
            </div>
        </div>
    </div>
</template>