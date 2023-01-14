<template>
  <div class="w-full py-4 flex flex-col gap-12">
    <h-b>KIBERone - это </h-b>
    <div class=" w-full grid grid-cols-2 gap-4 sm:gap-0 sm:grid-cols-4">
      <div
        v-for="(item, i) in w1"
        :key="i"
        class="flex flex-col gap-2 justify-center items-center"
      >
        <span class="text-2xl sm:text-4xl font-bold text-center">{{ item.name }}</span>
        <span class="text-center text-gray-500">{{ item.subName }}</span>
      </div>
    </div>
  </div>
</template>

<script>
import hb from './h-b.vue'

export default {
  components: { hb },
  data () {
    return {
      w1: [
        { name: '30', subName: ' стран' },
        { name: '300', subName: 'городов' },
        { name: '80%', subName: ' занятий практика' },
        { name: 'от 3000$', subName: 'з/п специалиста' }
      ]
    }
  }
}
</script>

<style></style>
