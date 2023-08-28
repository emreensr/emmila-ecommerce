<template>
  <client-only>
    <Swiper
      class="first-swiper"
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
      <swiper-slide
        v-if="!isMobile"
        class="relative"
        v-for="photo in swiperData"
        :key="photo.id"
      >
        <img class="h-custom w-full object-cover" :src="photo.img" />
      </swiper-slide>
      <swiper-slide
        v-if="isMobile"
        class="relative"
        v-for="photo in mobileSwiperData"
        :key="photo.id"
      >
        <img class="h-custom w-full object-cover" :src="photo.img" />
      </swiper-slide>
      <div class="swiper-button-next">
        <svg
          stroke="currentColor"
          fill="currentColor"
          stroke-width="0"
          viewBox="0 0 16 16"
          color="#fff"
          height="30"
          width="30"
          xmlns="http://www.w3.org/2000/svg"
          style="color: rgb(255, 255, 255)"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M9 13.887l5-5V8.18l-5-5-.707.707 4.146 4.147H2v1h10.44L8.292 13.18l.707.707z"
          ></path>
        </svg>
      </div>
      <div class="swiper-button-prev">
        <svg
          stroke="currentColor"
          fill="currentColor"
          stroke-width="0"
          viewBox="0 0 16 16"
          color="#fff"
          height="30"
          width="30"
          xmlns="http://www.w3.org/2000/svg"
          style="color: rgb(255, 255, 255)"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M7 3.093l-5 5V8.8l5 5 .707-.707-4.146-4.147H14v-1H3.56L7.708 3.8 7 3.093z"
          ></path>
        </svg>
      </div>
    </Swiper>
  </client-only>
</template>

<script setup>
const swiperData = ref([
  {
    id: 1,
    img: "https://cdn.myikas.com/images/theme-images/512a2c80-abef-43ab-a545-7cdc468d4339/image_2560.webp",
  },
  {
    id: 2,
    img: "https://cdn.myikas.com/images/theme-images/512a2c80-abef-43ab-a545-7cdc468d4339/image_2560.webp",
  },
  {
    id: 3,
    img: "https://cdn.myikas.com/images/theme-images/512a2c80-abef-43ab-a545-7cdc468d4339/image_2560.webp",
  },
]);

const mobileSwiperData = ref([
  {
    id: 1,
    img: "https://cdn.myikas.com/images/theme-images/747748bb-8140-4216-8d88-3fd4de135761/image_720.webp",
  },
  {
    id: 2,
    img: "https://cdn.myikas.com/images/theme-images/747748bb-8140-4216-8d88-3fd4de135761/image_720.webp",
  },
  {
    id: 3,
    img: "https://cdn.myikas.com/images/theme-images/747748bb-8140-4216-8d88-3fd4de135761/image_720.webp",
  },
]);

const isMobile = ref(false);

watchEffect(() => {
  if (process.client) {
    isMobile.value = window.innerWidth <= 768;

    window.addEventListener("resize", () => {
      isMobile.value = window.innerWidth <= 768;
    });
  }
});
console.log(isMobile.value);
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

.first-swiper .swiper-button-prev {
  left: 38px !important;
  background-repeat: no-repeat;
  background-color: black;
  border-radius: 5px;
  width: 48px;
  padding: 5px;
  height: 48px;
}

.first-swiper .swiper-button-next {
  right: 38px !important;
  width: 48px;
  height: 48px;
  background-color: black;
  background-repeat: no-repeat;
  border-radius: 5px;
  padding: 5px;
}

.first-swiper .swiper-button-next::after,
.first-swiper .swiper-button-prev::after {
  content: "";
  display: none;
}

@media only screen and (max-width: 767px) and (min-width: 375px) {
  .first-swiper .swiper-button-prev {
    display: none;
  }

  .first-swiper .swiper-button-next {
    display: none;
  }
}

.h-custom {
  max-height: calc(100vh - 125px);
}
</style>
