<template>
  <div class=" bg-white drop-shadow-xl fixed top-0 left-0 right-0 z-[4]">
    <div class="flex justify-between items-center py-4 container">
      <nuxt-link to="/">
        <img src="~/assets/img/logo.png" alt="" class=" w-full h-auto" />
      </nuxt-link>
      <div class="hidden sm:block">
        <span class="flex items-center gap-2"
          ><svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 6.75c0 8.284 6.716 15 15 15h2.25a2.25 2.25 0 002.25-2.25v-1.372c0-.516-.351-.966-.852-1.091l-4.423-1.106c-.44-.11-.902.055-1.173.417l-.97 1.293c-.282.376-.769.542-1.21.38a12.035 12.035 0 01-7.143-7.143c-.162-.441.004-.928.38-1.21l1.293-.97c.363-.271.527-.734.417-1.173L6.963 3.102a1.125 1.125 0 00-1.091-.852H4.5A2.25 2.25 0 002.25 4.5v2.25z"
            />
          </svg>
          +7 (8652) 91-58-78</span
        >
      </div>
      <div>
        <button
        @click="openmodal"
          class="border-2 border-purple-500 text-sm sm:text-xl font-semibold px-5 py-2 rounded-md flex justify-center items-center gap-2"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="w-4 h-4 rotate-45 text-purple-500"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"
            />
          </svg>
          <span class="hidden sm:block pb-[1px] text-purple-500 font-bold"
            >Записаться на пробное занятие</span
          >
          <span class="sm:hidden block pb-[1px] text-purple-500 font-bold"
            >Записаться</span
          >
        </button>
      </div>
    </div>
    
  </div>
</template>

<script>

export default {
  components: {  },
  data () {
    return {
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
  methods: {
    openmodal(){
      this.$emit('openModal')
    },
    
  },
}
</script>

<style></style>
