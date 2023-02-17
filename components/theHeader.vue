<template>
  <div class="bg-white drop-shadow-xl fixed top-0 left-0 right-0 z-[4]">
    <div class="flex justify-between items-center py-2 sm:py-4 container">
      <div class="flex items-center gap-2">
        <nuxt-link to="/">
          <img
            src="~/assets/img/logo.png"
            alt=""
            class="w-full max-w-[80px] sm:max-w-[140px] h-auto"
          />
        </nuxt-link>

        <div class="hidden sm:flex flex-col">
          <span class="text-xl">г. Ставрополь</span>
          <span>ул. Ленина, 282</span>
          <span>ул. 50 лет ВЛКСМ, 68</span>
        </div>
      </div>
      <button
        @click="menuOpen = !menuOpen"
        class="flex sm:hidden items-center justify-end gap-1"
      >
        МЕНЮ
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-8 h-8"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
          />
        </svg>
      </button>
      <span class="hidden sm:block text-lg font-bold text-purple-500"
        >Бесплатная пробная неделя до 26 марта!</span
      >

      <div class="hidden sm:flex flex-col justify-end items-end">
        <span class="flex items-center gap-2"
          ><svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-5 h-5"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z"
            />
          </svg>
          <a href="tel:89887485878" class="font-bold text-lg"
            >+7 (988) 748-58-78</a
          >
        </span>
      </div>
    </div>
    <!-- modal -->
    <div
      v-if="menuOpen"
      class="w-screen h-screen bg-white px-4 py-2 fixed z-[6] top-0 left-0 right-0 flex flex-col justify-start items-start"
    >
      <div class="flex items-center gap-2 w-full">
        <div class="flex items-center justify-between w-full">
          <nuxt-link to="/">
            <img
              src="~/assets/img/logo.png"
              alt=""
              class="w-full max-w-[80px] h-auto"
            />
          </nuxt-link>
          <button
            @click="menuOpen = !menuOpen"
            class="flex items-center justify-end gap-1"
          >
            МЕНЮ
            <svg
              xmlns="http://www.w3.org/2000/svg"
              fill="none"
              viewBox="0 0 24 24"
              stroke-width="1.5"
              stroke="currentColor"
              class="w-8 h-8"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
      <div class="flex flex-col gap-4 mt-6">
        <span class="block text-lg font-bold text-purple-500 text-center"
          >Бесплатная пробная неделя до 26 марта!</span
        >
        <nuxt-link to="/contacts">Контакты</nuxt-link>
        <a
          href="tel:89887485878"
          class="text-white bg-purple-500 text-lg w-full text-center py-2 rounded-md"
          >+7 (988) 748-58-78</a
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data () {
    return {
      menuOpen: false,
      menu: [
        {
          name: 'Тьюторы',
          link: '/'
        },
        {
          name: '2',
          link: '/'
        },
        {
          name: '3',
          link: '/'
        },
        {
          name: '4',
          link: '/'
        }
      ]
    }
  },
  methods: {}
}
</script>

<style></style>
