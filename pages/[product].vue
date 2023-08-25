<template>
    <div>
        <div class="grid grid-cols-1 lg:grid-cols-4 gap-5 mx-auto max-w-7xl lg:pt-24 pt:12 px-3">
            <div class="col-span-1">
                <div class="flex items-center space-x-2 mt-5">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4" viewBox="0 0 512 512">
                        <path
                            d="M3.9 54.9C10.5 40.9 24.5 32 40 32H472c15.5 0 29.5 8.9 36.1 22.9s4.6 30.5-5.2 42.5L320 320.9V448c0 12.1-6.8 23.2-17.7 28.6s-23.8 4.3-33.5-3l-64-48c-8.1-6-12.8-15.5-12.8-25.6V320.9L9 97.3C-.7 85.4-2.8 68.8 3.9 54.9z" />
                    </svg>
                    <h1 class="font-medium text-xl">FİLTRE</h1>
                </div>
                <div>
                    <div class="py-6">
                        <h3 class="-mx-2 -my-3 flow-root">
                            <button type="button" @click="togglePriceFilter"
                                class="flex w-full items-center justify-between bg-white px-2 py-3 text-gray-400 hover:text-gray-500"
                                aria-controls="filter-section-mobile-0" aria-expanded="false">
                                <span class="font-medium text-gray-900">Fiyat Aralığı</span>
                                <span class="ml-6 flex items-center transform duration-300 relative">
                                    <div class="w-3 bg-gray-400 h-0.5">
                                    </div>
                                    <div :class="showPriceFilter ? 'rotate-0' : 'rotate-90'" class="w-3 bg-gray-400 h-0.5 absolute transform duration-200">
                                    </div>
                                </span>
                            </button>
                        </h3>
                        <transition mode="out-in" enter-active-class="transition duration-300 transform"
                            enter-from-class="opacity-0 translate-y-[-10%]" enter-to-class="opacity-100 translate-y-0"
                            leave-active-class="transition duration-300 transform"
                            leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-[-10%]">
                            <div v-if="showPriceFilter" class=" overflow-y-hidden" id="filter-section-mobile-0">
                                <div class="pt-5">
                                    <ul class="flex w-full justify-between mt-2">
                                        <li class="text-gray-500 text-sm" v-for="price in priceList">{{ price }}₺</li>
                                    </ul>
                                    <input v-model="selectedMinPrice"
                                        class="range-slider w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer"
                                        type="range" min="0" max="1000" step="10">
                                    <p class="text-gray-600">Minimum Fiyat: {{ selectedMinPrice }}₺</p>
                                    <hr class="my-3">
                                    <ul class="flex w-full justify-between my-1">
                                        <li class="text-gray-500 text-sm" v-for="price in priceList">{{ price }}₺</li>
                                    </ul>
                                    <input v-model="selectedMaxPrice"
                                        class="range-slider w-full h-2 bg-gray-200 rounded-lg appearance-none cursor-pointer"
                                        type="range" min="0" max="1000" step="10">
                                    <p class="text-gray-600">Maksimum Fiyat: {{ selectedMaxPrice }}₺</p>
                                </div>
                            </div>
                        </transition>
                    </div>
                    <div class="border-t border-gray-200 py-6 transform transition-all duration-300">
                        <h3 class="-mx-2 -my-3 flow-root">
                            <button type="button" @click="toggleColorFilter"
                                class="flex w-full items-center justify-between bg-white px-2 py-3 text-gray-400 hover:text-gray-500"
                                aria-controls="filter-section-mobile-0" aria-expanded="false">
                                <span class="font-medium text-gray-900">Renk</span>
                                <span class="ml-6 flex items-center transform duration-300 relative">
                                    <div class="w-3 bg-gray-400 h-0.5">
                                    </div>
                                    <div :class="showColorFilter ? 'rotate-0' : 'rotate-90'" class="w-3 bg-gray-400 h-0.5 absolute transform duration-200">
                                    </div>
                                </span>
                            </button>
                        </h3>
                        <transition mode="out-in" enter-active-class="transition duration-300 transform"
                            enter-from-class="opacity-0 translate-y-[-10%]" enter-to-class="opacity-100 translate-y-0"
                            leave-active-class="transition duration-300 transform"
                            leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-[-10%]">
                            <div v-if="showColorFilter" class="pt-5 overflow-y-hidden" id="filter-section-mobile-0">
                                <div class="space-y-4">
                                    <div v-for="color in colorList" class="flex items-center">
                                        <input id="filter-mobile-color-0" name="color[]" value="{{color}}" type="checkbox"
                                            class="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500">
                                        <label for="filter-mobile-color-0" class="ml-3 min-w-0 flex-1 text-gray-500">{{
                                            color }}</label>
                                    </div>
                                </div>
                            </div>
                        </transition>
                    </div>
                    <div class="border-t border-gray-200 py-6 transform transition-all duration-300">
                        <h3 class="-mx-2 -my-3 flow-root">
                            <button type="button" @click="toggleTypeFilter"
                                class="flex w-full items-center justify-between bg-white px-2 py-3 text-gray-400 hover:text-gray-500"
                                aria-controls="filter-section-mobile-0" aria-expanded="false">
                                <span class="font-medium text-gray-900">Tipi</span>
                                <span class="ml-6 flex items-center transform duration-300 relative">
                                    <div class="w-3 bg-gray-400 h-0.5">
                                    </div>
                                    <div :class="showTypeFilter ? 'rotate-0' : 'rotate-90'" class="w-3 bg-gray-400 h-0.5 absolute transform duration-200">
                                    </div>
                                </span>
                            </button>
                        </h3>
                        <transition mode="out-in" enter-active-class="transition duration-300 transform"
                            enter-from-class="opacity-0 translate-y-[-10%]" enter-to-class="opacity-100 translate-y-0"
                            leave-active-class="transition duration-300 transform"
                            leave-from-class="opacity-100 translate-y-0" leave-to-class="opacity-0 translate-y-[-10%]">
                            <div v-if="showTypeFilter" class="pt-5 overflow-y-hidden" id="filter-section-mobile-0">
                                <div class="space-y-4">
                                    <div v-for="tip in typeList" class="flex items-center">
                                        <input id="filter-mobile-color-0" name="color[]" value="{{tip}}" type="checkbox"
                                            class="h-4 w-4 rounded border-gray-300 text-indigo-600 focus:ring-indigo-500">
                                        <label for="filter-mobile-color-0" class="ml-3 min-w-0 flex-1 text-gray-500">{{
                                            tip }}</label>
                                    </div>
                                </div>
                            </div>
                        </transition>
                    </div>
                </div>
            </div>
            <div class="grid col-span-1 grid-cols-2 lg:col-span-3 lg:grid-cols-3 gap-5">
                <div class="relative" v-for="product in productData">
                    <span v-if="product.stock < 1" class="absolute top-o right-0 border p-1 bg-black text-white text-sm ">Tükendi</span>
                    <img
                        :src="product.image" />
                    <button
                        class="transition duration-300 bottom-3 w-full py-3 left-0 bg-black text-sm font-semibold text-white" :class="product.stock < 1 && 'cursor-not-allowed bg-[#ececec] text-black'" :disabled="product.stock < 1">
                        <span v-if="product.stock > 0" 
                              class="font-bold">
                            SEPETE EKLE
                        </span>
                        <span v-if="product.stock < 1" 
                              class="font-bold">
                            STOKTA YOK
                        </span>
                    </button>
                    <div class="flex justify-between items-center mt-3">
                        <h3 class="font-bold my-2">{{product.name}}</h3>
                        <p class="font-bold text-xl">{{product.price}}₺</p>
                    </div>
                    <p class="text-md">{{product.description}}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const route = useRoute()
const showColorFilter = ref(false)
const showPriceFilter = ref(false)
const showTypeFilter = ref(false)

const productData = ref([{
    id:1,
    image:"https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/b97b28cd-4790-4332-bed6-9e4fbc74432c/image_720.webp",
    name:"Emmila",
    price:2200,
    description:"Emmila Crossbody Croc Black",
    stock : 20,
},
{
    id:2,
    image:"https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/b97b28cd-4790-4332-bed6-9e4fbc74432c/image_720.webp",
    name:"Emmila",
    price:12000,
    description:"Emmila Crossbody Croc Black",
    stock : 0,
},
{
    id:3,
    image:"https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/b97b28cd-4790-4332-bed6-9e4fbc74432c/image_720.webp",
    name:"Emmila",
    price:5000,
    description:"Emmila Crossbody Croc Black",
    stock : 20,
},
{
    id:4,
    image:"https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/b97b28cd-4790-4332-bed6-9e4fbc74432c/image_720.webp",
    name:"Emmila",
    price:2000,
    description:"Emmila Crossbody Croc Black",
    stock : 0,
},])

const priceList = ref([
    '0',
    '200',
    '400',
    '600',
    '800',
    '1000'
]);

const colorList = ref([
    'Kırmızı',
    'Siyah',
    'Beyaz',
    'Gri',
    'Yeşil',
    'Mavi'
]);
const typeList = ref([
    'Sırt Çantası',
    'Bel Çantası',
    'El Çantası',
    'Postacı Çantası',
    'Niko Çantası',
    'Zehir Çantası'
]);

const toggleColorFilter = () => {
    showColorFilter.value = !showColorFilter.value;
}
const togglePriceFilter = () => {
    showPriceFilter.value = !showPriceFilter.value;
}
const toggleTypeFilter = () => {
    showTypeFilter.value = !showTypeFilter.value;
}

const selectedMinPrice = ref(0);
const selectedMaxPrice = ref(0);
</script>

<style>
.range-slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 16px;
    height: 16px;
    background-color: black;
    border: none;
    border-radius: 50%;
    cursor: pointer;
}
</style>