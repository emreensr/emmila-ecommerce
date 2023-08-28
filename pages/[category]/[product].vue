<template>
    <div>
        <div class="grid grid-cols-1 lg:grid-cols-6 gap-5 mx-auto max-w-8xl lg:pt-20 pt:12 px-3">
            <div class="col-span-1">
                <div class="h-30 w-30">
                    <img src="https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/abe2a1c7-1893-44a1-93fd-d36a65cf633e/image_540.webp"
                        class="object-cover" />
                </div>
            </div>
            <div class="col-span-3">
                <client-only>
    <Swiper
    :modules="[
      SwiperAutoplay,
      SwiperEffectCreative,
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
    :navigation="{
      clickable: true,
      nextEl: '.swiper-button-next',
      prevEl: '.swiper-button-prev',
    }"
  >
    <swiper-slide v-if="!isMobile" class="relative" v-for="photo in productImages" :key="photo.id">
      <img class="h-custom w-full object-cover" :src="photo.img" />
    </swiper-slide>
    <div class="swiper-button-next"></div>
    <div class="swiper-button-prev"></div>
  </Swiper>
  </client-only>
                <div class="">
                    <img src="https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/abe2a1c7-1893-44a1-93fd-d36a65cf633e/image_540.webp"
                        class="object-cover w-full" />
                </div>
            </div>
            <div class="col-span-2">
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
                <div class="flex mt-5">
                    <div class="flex flex-1 space-x-8 text-xl items-center">
                        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="1em"
                            width="1em" xmlns="http://www.w3.org/2000/svg">
                            <path d="M5 11h14v2H5z"></path>
                        </svg>
                        <span class="text-md">1</span>
                        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="1em"
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
                <div class="border-t border-gray-200 py-6 transform transition-all duration-300">
                    <h3 class="-mx-2 -my-3 flow-root">
                        <button type="button" @click="toggleDescription"
                            class="flex w-full items-center justify-between bg-white px-2 py-3 text-gray-400 hover:text-gray-500"
                            aria-controls="filter-section-mobile-0" aria-expanded="false">
                            <span class="font-medium text-gray-900 hover:underline hover:underline-offset-1">Ürün Açıklaması</span>
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
                                <div class="flex items-center">
                                    <p>Pels Basic Pouch, Pels Side Pocket Crossbody iPhone kılıfınız için mükemmel bir
                                        eklentidir. Pasaportunuz, anahtarınız, makyaj malzemeniz, not defteriniz ve çok daha
                                        fazlası için sahip olunması gereken bir el çantasıdır. Halkaları sayesinde Pels Side
                                        Pocket Crossbody iPhone kılıfınıza kolayca eklenebilir. İster tek başına elinizde ya
                                        da çantanızın içinde cüzdan olarak, ister kılıfınızla birlikte kullanabilme şansına
                                        sahipsiniz.
                                        İhtiyacın olan her şey yanında!
                                        Ürün Özellikleri:
                                        Ölçüler: 20 X 12 X 1 cm
                                        Orjinal Deri
                                        Astar: Siyah Polyester Astar
                                        Gümüş aksesuar
                                        El çantası olarak ya da Pels Side Pocket Crossbody telefon kılıfınıza eklenti olarak
                                        kullanılabilir.
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
const showDescription = ref(false)

const toggleDescription = () => {
    showDescription.value = !showDescription.value;
}

const productImages = ref([
  {
    id:1,
    img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/abe2a1c7-1893-44a1-93fd-d36a65cf633e/image_540.webp",
  },
  {
    id:2,
    img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/abe2a1c7-1893-44a1-93fd-d36a65cf633e/image_540.webp",
  },
  {
    id:3,
    img: "https://cdn.myikas.com/images/c92faa73-5650-4267-9e11-9aac520a912b/abe2a1c7-1893-44a1-93fd-d36a65cf633e/image_540.webp",
  },
]);
</script>


<style lang="scss">

    .swiper-button-prev {
    @apply bg-black text-white w-10 h-12 rounded-lg;
    }
    .swiper-button-next {
    @apply bg-black text-white w-10 h-12 px-3 rounded-lg;
    }
    .h-custom {
    max-height: calc(100vh - 125px);
    }
</style>