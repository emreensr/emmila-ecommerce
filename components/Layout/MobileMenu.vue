<template>
  <div class="fixed w-full h-full bg-white z-40">
    <div class="flex justify-between items-center p-5">
      <div class="flex space-x-3">
        <svg
          class="cursor-pointer"
          @click="closeMenu"
          stroke="currentColor"
          fill="currentColor"
          stroke-width="0"
          viewBox="0 0 24 24"
          height="25"
          width="25"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path fill="none" d="M0 0h24v24H0z"></path>
          <path
            d="M19 6.41L17.59 5 12 10.59 6.41 5 5 6.41 10.59 12 5 17.59 6.41 19 12 13.41 17.59 19 19 17.59 13.41 12z"
          ></path>
        </svg>
        <nuxt-link class="font-bold"> ÜYE GİRİŞİ </nuxt-link>
        <nuxt-link class="font-bold"> KAYIT OL </nuxt-link>
      </div>
      <div>
        <svg
          stroke="currentColor"
          fill="currentColor"
          stroke-width="0"
          viewBox="0 0 24 24"
          color="#000000ff"
          height="25"
          width="25"
          xmlns="http://www.w3.org/2000/svg"
          style="color: rgb(0, 0, 0)"
        >
          <g>
            <path fill="none" d="M0 0h24v24H0z"></path>
            <path
              d="M7 8V6a5 5 0 1 1 10 0v2h3a1 1 0 0 1 1 1v12a1 1 0 0 1-1 1H4a1 1 0 0 1-1-1V9a1 1 0 0 1 1-1h3zm0 2H5v10h14V10h-2v2h-2v-2H9v2H7v-2zm2-2h6V6a3 3 0 0 0-6 0v2z"
            ></path>
          </g>
        </svg>
      </div>
    </div>
    <div class="p-5">
      <ul class="space-y-6 uppercase font-extralight">
        <li
          v-for="product in products"
          :key="product.id"
          class="flex justify-between"
        >
          <nuxt-link :to="`/${product.slug}`" @click="closeMenu"
          >
            {{ product.name }}
          </nuxt-link>
          <svg
            stroke="currentColor"
            fill="currentColor"
            stroke-width="0"
            viewBox="0 0 24 24"
            color="#000000ff"
            height="30"
            width="30"
            xmlns="http://www.w3.org/2000/svg"
            style="color: rgb(0, 0, 0)"
          >
            <path fill="none" d="M0 0h24v24H0z"></path>
            <path d="M10 6L8.59 7.41 13.17 12l-4.58 4.59L10 18l6-6z"></path>
          </svg>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
const { closeMenu } = defineProps(["closeMenu"]);
const showMenu = ref(true)
const products = ref([
  {
    id: 1,
    name: "emmila",
    slug: "emmila",
  },
  {
    id: 2,
    name: "Telefon Kılıfı",
    slug: "telefon-kilifi",
  },
  {
    id: 3,
    name: "çanta",
    slug: "canta",
  },
  {
    id: 4,
    name: "cüzdan",
    slug: "cuzdan",
  },
  {
    id: 5,
    name: "kemer",
    slug: "kemer",
  },
]);
</script>
