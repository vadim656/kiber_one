<template>
  <div class="bg-[#FBF8FB] relative">
    <f-modal ref="modalForm">
      <div class="grid grid-cols-1 gap-3 w-full max-w-[300px]">
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
        <div class="flex flex-col gap-1 w-full">
          <label for="">Возраст ребенка </label>
          <div class="border p-2 rounded-md flex justify-between items-center">
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
          <span class=" pb-[1px] text-purple-500 font-bold">ОТПРАВИТЬ</span>
        </button>
        <span v-if="succes == true" class="text-center text-sm ">Спасибо! Наш менеджер перезвонит Вам в течение 15 минут.</span>
        <span class="text-slate-400 text-xs text-center"
          >Нажимая "Отправить", вы соглашаетесь с Политикой обработки
          персональных данных</span
        >
      </div>
    </f-modal>
    <the-header @openModal="openModal" />
    <div class="container bg-[#FBF8FB] flex flex-col gap-12  pt-32">
      <main-slides @openModal="openModal" />
      <block-4 />
      <block-1 @scroll1="scroll1" @openmodal2="openmodal2" />
      <block-2 id="block2" />
      <block-3 />
      <block-5 />
    </div>
    <the-footer />
  </div>
</template>

<script>
import fModal from '~/components/f-modal.vue'
import Block1 from '~/components/block1.vue'
import Block2 from '~/components/block2.vue'
import Block3 from '~/components/block3.vue'
import Block4 from '~/components/block4.vue'
import Block5 from '~/components/block5.vue'
import MainSlides from '~/components/mainSlides.vue'
import TheHeader from '~/components/theHeader.vue'
import TheFooter from '~/components/theFooter.vue'
export default {
  name: 'IndexPage',
  components: {
    TheHeader,
    MainSlides,
    Block1,
    Block2,
    Block3,
    Block4,
    Block5,
    fModal,
    TheFooter
  },
  data () {
    return {
      succes: false,
      errors: [],
      form: {
        name: '',
        phone: '',
        vozrast: 6
      }
    }
  },
  methods: {
    scroll1 () {
      setTimeout(() => {
        let scrollDiv = document.getElementById('block2').offsetTop - 90
        window.scrollTo({ top: scrollDiv, behavior: 'smooth' })
        console.log(scrollDiv.offsetTop - 50)
      }, 300)
    },
    openModal () {
      this.$refs.modalForm.active = true
    },
    openmodal2 () {
      this.$refs.modalForm.active = true
      console.log('opn');
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
        'Заявка с формы модальное' +
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
          setTimeout(() => (this.$refs.modalForm.active = false, this.succes = false), 1000)
        })
        .catch(e => {
          this.errors.push(e)
        })
    }
  }
}
</script>
