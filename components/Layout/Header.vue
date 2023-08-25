<template>

    <LayoutOffCanvasCart v-if="isOpen" :isOpen="isOpen" :closeCart="openCartToggle" />


  <transition mode="out-in" enter-active-class="transition duration-300 transform"
    enter-from-class="opacity-0 translate-x-[-100%]" enter-to-class="opacity-100 translate-x-0"
    leave-active-class="transition duration-300 transform" leave-from-class="opacity-100 translate-x-0"
    leave-to-class="opacity-0 translate-x-[-100%]">
    <LayoutMobileMenu v-if="showMobileMenu" :closeMenu="closeMobileMenu" />
  </transition>

  <div class="w-full h-10 bg-black flex items-center justify-center">
    <h3 class="text-white font-semibold text-lg">#ALBİZDEN</h3>
  </div>
  <div class="flex justify-between items-center py-5 lg:px-20 px-4">
    <div class="flex justify-center items-center gap-2">
      <svg @click="showMobileMenu = true" class="md:hidden cursor-pointer" stroke="currentColor" fill="currentColor"
        stroke-width="0" viewBox="0 0 20 20" height="25" width="25" xmlns="http://www.w3.org/2000/svg">
        <path fill-rule="evenodd"
          d="M3 7a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1zM3 13a1 1 0 011-1h12a1 1 0 110 2H4a1 1 0 01-1-1z"
          clip-rule="evenodd"></path>
      </svg>
      <nuxt-link :to="'/'" class="text-3xl lg:text-4xl capitalize font-mono">emmila</nuxt-link>
    </div>
    <div class="hidden md:block">
      <ul class="flex space-x-4 text-md uppercase">
        <nuxt-link :to="`/${product.slug}`" v-for="product in products">{{ product.name }}</nuxt-link>
      </ul>
    </div>
    <div class="flex space-x-5">
      <div>
        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" color="#000000ff" height="25"
          width="25" xmlns="http://www.w3.org/2000/svg" style="color: rgb(0, 0, 0)">
          <g>
            <path fill="none" d="M0 0h24v24H0z"></path>
            <path
              d="M18.031 16.617l4.283 4.282-1.415 1.415-4.282-4.283A8.96 8.96 0 0 1 11 20c-4.968 0-9-4.032-9-9s4.032-9 9-9 9 4.032 9 9a8.96 8.96 0 0 1-1.969 5.617zm-2.006-.742A6.977 6.977 0 0 0 18 11c0-3.868-3.133-7-7-7-3.868 0-7 3.132-7 7 0 3.867 3.132 7 7 7a6.977 6.977 0 0 0 4.875-1.975l.15-.15z">
            </path>
          </g>
        </svg>
      </div>
      <div>
        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" color="#000000ff" height="25"
          width="25" xmlns="http://www.w3.org/2000/svg" style="color: rgb(0, 0, 0)">
          <g>
            <path fill="none" d="M0 0h24v24H0z"></path>
            <path
              d="M20 22h-2v-2a3 3 0 0 0-3-3H9a3 3 0 0 0-3 3v2H4v-2a5 5 0 0 1 5-5h6a5 5 0 0 1 5 5v2zm-8-9a6 6 0 1 1 0-12 6 6 0 0 1 0 12zm0-2a4 4 0 1 0 0-8 4 4 0 0 0 0 8z">
            </path>
          </g>
        </svg>
      </div>
      <div class="relative cursor-pointer" @click="openCartToggle">
        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" color="#000000ff" height="25"
          width="25" xmlns="http://www.w3.org/2000/svg" style="color: rgb(0, 0, 0)">
          <g>
            <path fill="none" d="M0 0h24v24H0z"></path>
            <path
              d="M7 8V6a5 5 0 1 1 10 0v2h3a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1H4a1 1 0 0 1-1-1V9a1 1 0 0 1 1-1h3zm0 2H5v10h14V10h-2v2h-2v-2H9v2H7v-2zm2-2h6V6a3 3 0 0 0-6 0v2z">
            </path>
          </g>
        </svg>
        <div
          class="bg-black absolute -top-1.5 -right-0.5 rounded-full w-4 h-4 text-white flex items-center justify-center">
          <span class="text-[10px] font-mono">1</span>
        </div>
      </div>
    </div>
  </div>
  <div class="w-full h-8 bg-black flex items-center justify-center">
    <marquee scrollamount="3" class="text-white text-[14px] space-x-10" loop="infinite" behavior="alternate"
      direction="left">
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
</template>

<script setup>

const isOpen = ref(false)

const openCartToggle = () => {
  isOpen.value = !isOpen.value;
}


const products = ref([
  {
    id: 1,
    name: "emmila",
    slug: "emmila"
  },
  {
    id: 2,
    name: "Telefon Kılıfı",
    slug: "telefon-kilifi"
  },
  {
    id: 3,
    name: "çanta",
    slug: "canta"
  },
  {
    id: 4,
    name: "cüzdan",
    slug: "cuzdan"
  },
  {
    id: 5,
    name: "kemer",
    slug: "kemer"
  }
]
)


const showMobileMenu = ref(false);

const closeMobileMenu = () => {
  showMobileMenu.value = false;
};
</script>
