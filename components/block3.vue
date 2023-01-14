<template>
  <div class="w-full py-4 flex flex-col gap-6">
    <h-b>Частые вопросы</h-b>
    <div class=" w-full">
      <div class="space-y-6">
        <details
          class="group rounded-xl bg-white p-6 shadow-[0_10px_100px_10px_rgba(0,0,0,0.05)]"
        >
          <summary
            class="flex cursor-pointer list-none items-center justify-between  text-sm sm:text-lg  font-bold text-secondary-900 py-2"
          >
            Когда проходят бесплатные пробные занятия?
            <div class="text-secondary-500">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="block h-5 w-5 transition-all duration-300 group-open:-rotate-90"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M8.25 4.5l7.5 7.5-7.5 7.5"
                />
              </svg>
            </div>
          </summary>
          <div class=" mt-2 text-sm sm:text-base  text-secondary-500">
            Занятия проходят каждый выходной день, но наличие свободных
            мест нужно уточнять у менеджера. Оставьте заявку в любой форме на
            сайте и он с вами свяжется для бронирования места. Занятие идет
            1 час.
          </div>
        </details>
        <details
          class="group rounded-xl bg-white p-6 shadow-[0_10px_100px_10px_rgba(0,0,0,0.05)]"
        >
          <summary
            class="flex cursor-pointer list-none items-center justify-between  text-sm sm:text-lg  font-bold text-secondary-900 py-2"
          >
            Для детей какого возраста проходит обучение?
            <div class="text-secondary-500">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="block h-5 w-5 transition-all duration-300 group-open:-rotate-90"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M8.25 4.5l7.5 7.5-7.5 7.5"
                />
              </svg>
            </div>
          </summary>
          <div class=" mt-2 text-sm sm:text-base  text-secondary-500">
            Программа обучение рассчитана на детей от 6 до 14 лет.
          </div>
        </details>
        <details
          class="group rounded-xl bg-white p-6 shadow-[0_10px_100px_10px_rgba(0,0,0,0.05)]"
        >
          <summary
            class="flex cursor-pointer list-none items-center justify-between  text-sm sm:text-lg  font-bold text-secondary-900 py-2"
          >
            Как часто проходят занятия?
            <div class="text-secondary-500">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke-width="1.5"
                stroke="currentColor"
                class="block h-5 w-5 transition-all duration-300 group-open:-rotate-90"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  d="M8.25 4.5l7.5 7.5-7.5 7.5"
                />
              </svg>
            </div>
          </summary>
          <div class=" mt-2 text-sm sm:text-base  text-secondary-500">
            Занятия проходят один раз в неделю 2 часа с небольшим перерывом. По
            выходным или будням. Это позволяет легко встраиваться в насыщенное
            расписание детей. Присутствие родителей на занятиях не требуется.
          </div>
        </details>
      </div>
    </div>
  </div>
</template>

<script>
import hb from './h-b.vue'
export default {
  components: { hb }
}
</script>

<style></style>
