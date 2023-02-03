<template>
  <div class="w-full py-4 flex flex-col gap-6">
    <div class=" bg-white p-3 rounded-3xl drop-shadow-2xl">
      <div
        class="bg-gradient-to-r from-purple-500 to-purple-600  grid grid-cols-1 gap-4 divide-y divide-purple-400 sm:divide-none sm:grid-cols-3 sm:gap-10 justify-items-center rounded-3xl p-6"
      >
        <div
          class="flex flex-col gap-3 justify-center items-center py-4 sm:py-0"
        >
          <span class="text-xl font-bold text-center text-white"
            >Бесплатное пробное занятие</span
          >
          <span @click="openmodal2" class="text-white cursor-pointer"
            >Подробнее</span
          >
        </div>
        <div
          class="flex flex-col gap-3 justify-center items-center py-4 sm:py-0"
        >
          <span class="text-xl font-bold text-center text-white"
            >Все модули обучения</span
          >
          <span @click="openmodal2" class="text-white cursor-pointer"
            >Подробнее</span
          >
        </div>
        <div
          class="flex flex-col gap-3 justify-center items-center py-4 sm:py-0"
        >
          <span class="text-xl font-bold text-center text-white"
            >Чему научится ребенок?</span
          >
          <span
            @click="scroll1"
            class="text-white cursor-pointer"
            target="_blank"
            >Подробнее</span
          >
        </div>
        
        <!-- <div
          class="flex flex-col gap-4 justify-center items-center py-2 sm:py-0"
        >
          <span class="text-2xl font-bold text-center text-white">Бесплатное пробное занятие</span>
          <span @click="openmodal2" class="text-white cursor-pointer" >Подробнее</span>
        </div> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    scroll1 () {
      this.$emit('scroll1')
    },
    openmodal2 () {
      this.$emit('openmodal2')
    }
  }
}
</script>

<style></style>
