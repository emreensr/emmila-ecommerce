<template>
    <!-- HEADER -->
    <div class="w-full h-8 bg-black flex items-center justify-center">
        <h3 class="text-white font-semibold text-xl">#ALBİZDEN</h3>
    </div>
    <div class="flex justify-between items-center py-4 px-6">
        <div class="text-4xl capitalize font-mono">
            emmila
        </div>
        <div class="">
            <ul class="flex space-x-4 text-sm uppercase">
                <li>
                    Emmila
                </li>
                <li>
                    telefon kıfı
                </li>
                <li>
                    çanta
                </li>
                <li>
                    cüzdan
                </li>
                <li>
                    kemer
                </li>
            </ul>
        </div>
        <div class="flex space-x-3">
            <div>
                <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" color="#000000ff"
                    height="25" width="25" xmlns="http://www.w3.org/2000/svg" style="color: rgb(0, 0, 0);">
                    <g>
                        <path fill="none" d="M0 0h24v24H0z"></path>
                        <path
                            d="M18.031 16.617l4.283 4.282-1.415 1.415-4.282-4.283A8.96 8.96 0 0 1 11 20c-4.968 0-9-4.032-9-9s4.032-9 9-9 9 4.032 9 9a8.96 8.96 0 0 1-1.969 5.617zm-2.006-.742A6.977 6.977 0 0 0 18 11c0-3.868-3.133-7-7-7-3.868 0-7 3.132-7 7 0 3.867 3.132 7 7 7a6.977 6.977 0 0 0 4.875-1.975l.15-.15z">
                        </path>
                    </g>
                </svg>
            </div>
            <div>
                <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" color="#000000ff"
                    height="25" width="25" xmlns="http://www.w3.org/2000/svg" style="color: rgb(0, 0, 0);">
                    <g>
                        <path fill="none" d="M0 0h24v24H0z"></path>
                        <path
                            d="M20 22h-2v-2a3 3 0 0 0-3-3H9a3 3 0 0 0-3 3v2H4v-2a5 5 0 0 1 5-5h6a5 5 0 0 1 5 5v2zm-8-9a6 6 0 1 1 0-12 6 6 0 0 1 0 12zm0-2a4 4 0 1 0 0-8 4 4 0 0 0 0 8z">
                        </path>
                    </g>
                </svg>
            </div>
            <div class="relative">
                <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" color="#000000ff"
                    height="25" width="25" xmlns="http://www.w3.org/2000/svg" style="color: rgb(0, 0, 0);">
                    <g>
                        <path fill="none" d="M0 0h24v24H0z"></path>
                        <path
                            d="M7 8V6a5 5 0 1 1 10 0v2h3a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1H4a1 1 0 0 1-1-1V9a1 1 0 0 1 1-1h3zm0 2H5v10h14V10h-2v2h-2v-2H9v2H7v-2zm2-2h6V6a3 3 0 0 0-6 0v2z">
                        </path>
                    </g>
                </svg>
                <div class="bg-black absolute -top-1.5 -right-0.5 rounded-full w-4 h-4 text-white flex items-center justify-center">
                    <span class="text-[10px] font-mono">1</span>
                </div>
            </div>
        </div>
    </div>
    <div class="w-full h-6 bg-black flex items-center justify-center">
        <marquee scrollamount="3" class="text-white text-[12px] space-x-10" loop="infinite" behavior="alternate" direction="left">
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
            <span>500 TL ÜZERİ KARGO BEDAVA</span>
        </marquee>
    </div>
    <!-- HEADER END -->
    <!-- HERO -->
    <Swiper
        :modules="[SwiperAutoplay, SwiperEffectCreative, SwiperPagination, SwiperNavigation]"
        :slides-per-view="1"
        :breakpoints="{ 
            640: {
                slidesPerView: 1
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

    <swiper-slide
      class="relative"
      v-for="photo in swiperData"
      :key="key"
    >
    <img 
    class="h-screen w-full object-cover"
    :src="photo.img" />
    </swiper-slide>
         <div class="swiper-button-next">
            <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" color="#fff" height="30" width="30" xmlns="http://www.w3.org/2000/svg" style="color: rgb(255, 255, 255);"><path fill-rule="evenodd" clip-rule="evenodd" d="M9 13.887l5-5V8.18l-5-5-.707.707 4.146 4.147H2v1h10.44L8.292 13.18l.707.707z"></path></svg>
         </div>
         <div class="swiper-button-prev"></div>
    </Swiper>

    <!-- HERO END -->
</template>

<script setup>
    const swiperData = ref([
        {
            img: 'https://cdn.myikas.com/images/theme-images/512a2c80-abef-43ab-a545-7cdc468d4339/image_2560.webp'
        },
        {
            img: 'https://cdn.myikas.com/images/theme-images/512a2c80-abef-43ab-a545-7cdc468d4339/image_2560.webp'
        },
        {
            img: 'https://cdn.myikas.com/images/theme-images/512a2c80-abef-43ab-a545-7cdc468d4339/image_2560.webp'
        }
    ]);

</script>

<style lang="scss">
.swiper-pagination-bullets {
    @apply flex justify-center pb-12 space-x-4 items-center w-full;

    .swiper-bullet {
        @apply bg-[#04121f24] h-2 w-2 cursor-pointer rounded-full mt-10;
    }

    .swiper-bullet-active {
        @apply bg-[#010C20] w-10;
    }
}

.swiper-button-prev {
    @apply bg-black text-white w-10 h-12 rounded-lg ;
}
.swiper-button-next {
    @apply bg-black text-black w-10 h-12 rounded-lg ;
}

</style>

