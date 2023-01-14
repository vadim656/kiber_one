<template>
  <div
    v-if="active"
    class="fixed flex justify-center items-center bg-[#343434]/40  w-screen h-screen left-0 top-0  z-[99] backdrop-blur-sm"
  >
    <div
      class="fixed  w-screen h-screen left-0 top-0 z-[7]"
      @click="active = !active"
    ></div>

    <div
      class="h-auto z-[8] bg-white px-4 py-6 rounded-md shadow-md flex flex-col gap-4 justify-center items-center fixed"
    >
      <span @click="active = !active" class="absolute top-3 right-3 cursor-pointer">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          fill="none"
          viewBox="0 0 24 24"
          stroke-width="1.5"
          stroke="currentColor"
          class="w-6 h-6"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </span>
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      active: false
    }
  }
}
</script>

<style></style>
