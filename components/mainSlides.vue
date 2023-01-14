<template>
  <div
    class="w-full py-4 flex flex-col sm:flex-row justify-center gap-6 sm:gap-24"
  >
    <div class="flex flex-col  justify-center gap-6 items-start">
      <div class="flex flex-col gap-2">
        <span class="text-3xl sm:text-4xl lg:text-5xl font-bold"
          >IT-школа для детей <br />
          от 6 до 14 лет</span
        >
        <span class="text-xl">в Ставрополе</span>
        <span class="text-xl font-bold mt-6">Бесплатное пробное занятие!</span>
      </div>
      <button
        @click="openmodal"
        class="bg-gradient-to-r from-purple-500 to-purple-600 text-white text-xl font-semibold px-5 py-2.5 rounded-md flex justify-center items-center gap-2"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-4 h-4 rotate-45"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M13.5 4.5L21 12m0 0l-7.5 7.5M21 12H3"
          />
        </svg>
        <span class="pb-[1px]">ЗАПИСАТЬСЯ</span>
      </button>
    </div>
    <div>
      <img
        src="~/assets/img/Frame2.jpg"
        alt=""
        class="rounded-2xl w-full h-auto"
      />
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    openmodal () {
      this.$emit('openModal')
    }
  }
}
</script>

<style></style>
