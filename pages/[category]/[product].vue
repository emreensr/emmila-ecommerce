<template>
    <div>
        <div class="grid grid-cols-1 lg:grid-cols-7 gap-5 mx-auto max-w-8xl lg:pt-12 mb-20 px-3">
            <div class="col-span-4">
                <client-only>
                    <Swiper
                        :modules="[
                            SwiperAutoplay,
                            SwiperEffectCreative,
                            SwiperPagination,
                            SwiperNavigation,
                        ]"
                        :slides-per-view="1"
                        :breakpoints="{
                            640: {
                            slidesPerView: 1,
                            },
                            768: {
                            slidesPerView: 1,
                            },
                            1024: {
                            slidesPerView: 1,
                            },
                        }"
                        :loop="true"
                        :autoplay="{ delay: 5000, disableOnInteraction: false }"
                        :pagination="{
                            clickable: true,
                            bulletClass: 'swiper-bullet',
                            bulletActiveClass: 'swiper-bullet-active',
                          }"
                        :navigation="{
                            clickable: true,
                            nextEl: '.swiper-button-next',
                            prevEl: '.swiper-button-prev',
                        }"
                        >
                        <swiper-slide class="relative" v-for="photo in productImages" :key="photo.id">
                            <img class="h-custom w-full object-cover" :src="photo.img" />
                        </swiper-slide>
                        <div class="swiper-button-next">
                            <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" color="#fff"
                                 xmlns="http://www.w3.org/2000/svg" style="color: rgb(255, 255, 255)">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M9 13.887l5-5V8.18l-5-5-.707.707 4.146 4.147H2v1h10.44L8.292 13.18l.707.707z"></path>
                            </svg>
                        </div>
                        <div class="swiper-button-prev">
                            <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" color="#fff"
                             xmlns="http://www.w3.org/2000/svg" style="color: rgb(255, 255, 255)">
                                <path fill-rule="evenodd" clip-rule="evenodd"
                                    d="M7 3.093l-5 5V8.8l5 5 .707-.707-4.146-4.147H14v-1H3.56L7.708 3.8 7 3.093z"></path>
                            </svg>
                        </div>
                    </Swiper>
                </client-only>
            </div>
            <div class="col-span-3">
                <div class="flex justify-between">
                    <div>
                        <h3 class="font-bold text-md">EMMILA</h3>
                        <p class="font-medium">Emmila Basic Pouch Classic Grey</p>
                    </div>
                    <div>
                        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="25"
                            width="25" xmlns="http://www.w3.org/2000/svg">
                            <g>
                                <path fill="none" d="M0 0H24V24H0z"></path>
                                <path
                                    d="M12.001 4.529c2.349-2.109 5.979-2.039 8.242.228 2.262 2.268 2.34 5.88.236 8.236l-8.48 8.492-8.478-8.492c-2.104-2.356-2.025-5.974.236-8.236 2.265-2.264 5.888-2.34 8.244-.228zm6.826 1.641c-1.5-1.502-3.92-1.563-5.49-.153l-1.335 1.198-1.336-1.197c-1.575-1.412-3.99-1.35-5.494.154-1.49 1.49-1.565 3.875-.192 5.451L12 18.654l7.02-7.03c1.374-1.577 1.299-3.959-.193-5.454z">
                                </path>
                            </g>
                        </svg>
                    </div>
                </div>
                <div class="mt-5">
                    <span class="font-bold text-lg mt-5">1250₺</span>
                </div>
                <div class="flex mt-5 gap-3">
                    <div class="flex space-x-8 text-xl items-center">
                        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="1em"
                            class="cursor-pointer"
                            width="1em" xmlns="http://www.w3.org/2000/svg">
                            <path d="M5 11h14v2H5z"></path>
                        </svg>
                        <span class="text-md">1</span>
                        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="1em"
                            class="cursor-pointer"
                            width="1em" xmlns="http://www.w3.org/2000/svg">
                            <path d="M19 11h-6V5h-2v6H5v2h6v6h2v-6h6z"></path>
                        </svg>
                    </div>
                    <div class="flex flex-[2]">
                        <button class="bg-black p-3 w-full text-white font-bold">SEPETE EKLE</button>
                    </div>
                </div>
                <div>
                    <button class="bg-black p-3 w-full text-white font-bold mt-3">HEMEN AL</button>
                </div>
                <div class="border-gray-200 mt-6 bg-[#fcfcfc] transform transition-all duration-300">
                    <h3 class="mx-1">
                        <button type="button" @click="toggleDescription"
                            class="flex w-full items-center justify-between px-2 py-3 text-[#fcfcfc] hover:text-[#fcfcfc]"
                            aria-controls="filter-section-mobile-0" aria-expanded="false">
                            <span class="font-medium text-gray-900 hover:underline hover:underline-offset-1">Ürün
                                Açıklaması</span>
                            <span class="ml-6 flex items-center transform duration-300 relative">
                                <div class="w-3 bg-gray-400 h-0.5">
                                </div>
                                <div :class="showDescription ? 'rotate-0' : 'rotate-90'"
                                    class="w-3 bg-gray-400 h-0.5 absolute transform duration-200">
                                </div>
                            </span>
                        </button>
                    </h3>
                    <transition mode="out-in" enter-active-class="transition duration-300 transform"
                        enter-from-class="opacity-0 translate-y-[-10%]" enter-to-class="opacity-100 translate-y-0"
                        leave-active-class="transition duration-300 transform" leave-from-class="opacity-100 translate-y-0"
                        leave-to-class="opacity-0 translate-y-[-10%]">
                        <div v-if="showDescription" class="pt-5 overflow-y-hidden" id="filter-section-mobile-0">
                            <div class="space-y-4">
                                <div class="items-center">
                                    <p class="text-sm p-3">Pels Basic Pouch, Pels Side Pocket Crossbody iPhone kılıfınız için mükemmel bir
                                        eklentidir. Pasaportunuz, anahtarınız, makyaj malzemeniz, not defteriniz ve çok daha
                                        fazlası için sahip olunması gereken bir el çantasıdır.<br> Halkaları sayesinde Pels Side
                                        Pocket Crossbody iPhone kılıfınıza kolayca eklenebilir. İster tek başına elinizde ya
                                        da çantanızın içinde cüzdan olarak, ister kılıfınızla birlikte kullanabilme şansına
                                        sahipsiniz.<br>
                                        İhtiyacın olan her şey yanında!<br>
                                        El çantası olarak ya da Pels Side Pocket Crossbody telefon kılıfınıza eklenti olarak
                                        kullanılabilir.<br>
                                        *Askı dahil değildir.</p>
                                </div>
                            </div>
                        </div>
                    </transition>
                </div>
            </div>

        </div>
    </div>
</template>

<script setup>
const showDescription = ref(true)

const toggleDescription = () => {
    showDescription.value = !showDescription.value;
}

const productImages = ref([
    {
        id: 1,
        img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/564e51ad-fd90-4d5e-abbe-aefef170dd7f/image_1728.webp",
    },
    {
        id: 2,
        img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/bc6b9245-4baf-45d2-9e84-6a3a6c825564/image_1728.webp",
    },
    {
        id: 3,
        img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/cfe1fb7a-75ba-4169-9938-9f2f67b6108c/image_1728.webp",
    },
    {
        id: 4,
        img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/e9757358-57d2-42bc-9ed8-9a00cdd358c8/image_1728.webp",
    },
]);
</script>

<style lang="scss">
.swiper-pagination-bullets {
    @apply flex justify-center lg:pb-12 space-x-4 items-center w-full;
  
    .swiper-bullet {
      @apply bg-white h-2 w-2 cursor-pointer rounded-full mt-10;
    }
  
    .swiper-bullet-active {
      @apply bg-[#010C20] lg:w-10 w-7;
    }
  }
  
.swiper-button-prev {
    left: 10px !important;
    background-repeat: no-repeat;
    background-color: black;
    border-radius: 5px;
    width: 40px;
    padding: 5px;
    height: 40px;
}

.swiper-button-next {
    right: 10px !important;
    width: 40px;
    height: 40px;
    background-color: black;
    background-repeat: no-repeat;
    border-radius: 5px;
    padding: 5px;
}

.swiper-button-next::after,
.swiper-button-prev::after {
    content: "";
    display: none;
}

@media only screen and (max-width: 767px) and (min-width: 375px) {
    .swiper-button-prev {
        display: none;
    }

    .swiper-button-next {
        display: none;
    }
}

@media only screen and (min-width: 767px) {
    .swiper-pagination-bullets {
        display: none;
    }

    .swiper-bullet {
        display: none;
    }
}



.h-custom {
    max-height: calc(100vh - 125px);
}
</style>