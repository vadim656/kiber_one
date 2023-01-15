<template>
  <div class="w-full py-4 flex flex-col gap-6">
    <h-b>Присоединиться к KIBERone</h-b>
    <div class="grid grid-cols-1 sm:grid-cols-[3fr,2fr] gap-4">
      <div class="hidden sm:block">
        <iframe
          src="https://yandex.ru/map-widget/v1/?um=constructor%3A77861484e0b4601fe7437087177b3aff25da3f0439628d86fe356532f1d1bb3a&amp;source=constructor"
          width="700"
          height="400"
          frameborder="0"
        ></iframe>
      </div>
      <div class="w-full bg-white p-6 rounded-md">
        <div class="grid grid-cols-1 gap-3">
          <div class="flex flex-col gap-1">
            <label for="">Имя* </label>
            <input
              v-model="form.name"
              type="text"
              class="border p-2 rounded-md"
            />
          </div>
          <div class="flex flex-col gap-1">
            <label for="">Телефон* </label>
            <input
              v-model="form.phone"
              type="text"
              class="border p-2 rounded-md"
              placeholder="+7"
              v-facade="'+7 (###) ###-##-##'"
            />
          </div>
          <div class="flex flex-col gap-1 w-full sm:max-w-[220px]">
            <label for="">Возраст ребенка </label>
            <div
              class="border p-2 rounded-md flex justify-between items-center"
            >
              <button
                @click="minus"
                class="py-2 px-4 bg-slate-200 flex justify-center items-center rounded-md"
              >
                -
              </button>
              <span class="text-sm">{{ form.vozrast }}</span>
              <button
                @click="plus"
                class="py-2 px-4 bg-slate-200 flex justify-center items-center rounded-md"
              >
                +
              </button>
            </div>
          </div>
          <button
            v-if="form.phone.length == 18 && form.name.length >= 2"
            class="border-2 border-purple-500 text-sm sm:text-lg font-semibold px-5 py-2 rounded-md flex justify-center items-center gap-2"
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

            <span
              @click="getTeelegrammToMain()"
              class=" pb-[1px] text-purple-500 font-bold"
              >ОТПРАВИТЬ</span
            >
          </button>
          <button
            v-else
            class="opacity-50 border-2 border-purple-500 text-sm sm:text-lg font-semibold px-5 py-2 rounded-md flex justify-center items-center gap-2"
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
            <span class=" pb-[1px] text-purple-500 font-bold">ОТПРАВИТЬ</span>
          </button>
          <span v-if="succes == true" class="text-center text-sm "
            >Спасибо! Наш менеджер перезвонит Вам в течение 15 минут.</span
          >
          <span class="text-slate-400 text-xs"
            >Нажимая "Отправить", вы соглашаетесь с Политикой обработки
            персональных данных</span
          >
        </div>
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
      form: {
        name: '',
        phone: '',
        vozrast: 6
      },
      w1: [
        { name: '30', subName: ' стран' },
        { name: '300', subName: 'городов' },
        { name: '80%', subName: ' занятий практика' },
        { name: 'от 3000$', subName: 'з/п специалиста' }
      ],
      succes: false,
      errors: []
    }
  },
  methods: {
    YMEventSendTgFooter() {
      this.$yandexMetrika.reachGoal('footer-form-tg');
    },
    plus () {
      if (this.form.vozrast < 14) {
        this.form.vozrast++
      }
    },
    minus () {
      if (this.form.vozrast > 6) {
        this.form.vozrast--
      }
    },
    async getTeelegrammToMain () {
      const fullMessege =
        'Заявка с формы подвал' +
        '\n' +
        'Телефон: ' +
        this.form.phone +
        '\n' +
        'Имя: ' +
        this.form.name +
        '\n' +
        'Возраст: ' +
        this.form.vozrast
      await this.$axios
        .post(
          'https://api.telegram.org/bot5959126365:AAFPC0KVUQeRFxclMIFeec2DtEhiEgSRiDw/sendMessage?chat_id=-1001842904151',
          {
            text: fullMessege
          }
        )
        .then(response => {
          this.form.phone = ''
          this.form.name = ''
          
          this.succes = true
          setTimeout(() => (this.succes = false), 1000)
          this.YMEventSendTgFooter()
        })
        .catch(e => {
          this.errors.push(e)
        })
    }
  }
}
</script>

<style></style>
