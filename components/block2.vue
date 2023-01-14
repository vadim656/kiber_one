<template>
  <div class="w-full py-4 flex flex-col gap-6">
    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 sm:gap-12 py-6 content-center">
      <client-only placeholder="Загрузка...">
        <agile :options="myOptions">
          <div class="slide">
            <img
              src="~/assets/img/Frame1.jpg"
              alt=""
              class="rounded-2xl w-full h-auto"
            />
          </div>
          <div class="slide">
            <img
              src="~/assets/img/Frame2.jpg"
              alt=""
              class="rounded-2xl w-full h-auto"
            />
          </div>
          <div class="slide">
            <img
              src="~/assets/img/Frame3.jpg"
              alt=""
              class="rounded-2xl w-full h-auto"
            />
          </div>
          <div class="slide">
            <img
              src="~/assets/img/Frame4.jpg"
              alt=""
              class="rounded-2xl w-full h-auto"
            />
          </div>
        </agile>
      </client-only>
      <div class="flex flex-col gap-6">
        <div class="flex flex-col gap-4">
          <span class="text-2xl sm:text-3xl font-bold w-full text-start">Ребенок получит навыки для успешного будущего:</span>

          <span class=""
            >KIBERone – место, где дети и подростки получают навыки и узнают всё
            о высоких технологиях</span
          >
        </div>
        <div class="grid grid-cols-2 gap-4 justify-items-center">
          <div
            v-for="(item, i) in grids"
            :key="i"
            class="cursor-pointer flex items-center justify-center w-full h-full border p-4 rounded-2xl hover:border-white drop-shadow-xl hover:drop-shadow-2xl bg-gradient-to-r from-slate-100 to-slate-50 hover:bg-slate-200 anime "
          >
            <div class=" text-slate-600 text-xs sm:text-sm text-center">
              {{ item.name }}
            </div>
          </div>
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
      myOptions: {
        navButtons: true,
        dots: true,
        centerMode: true,
        pauseOnHover: true
      },
      grids: [
        {
          name:
            'Работать в графических редакторах и совершенствоваться в области дизайна',
          subName: '1',
          icons: 'image10.png'
        },
        {
          name:
            'Создавать компьютерные игры, приложения и сайты для Web и Store',
          subName: '2',
          icons: 'image10.png'
        },
        {
          name: 'Создавать мультфильмы и монтировать видео',
          subName: '3',
          icons: 'image10.png'
        },
        {
          name:
            'Применять инструменты, которые используют в крупных IT-компаниях',
          subName: '4',
          icons: 'image10.png'
        },
        {
          name: 'Создавать искусственный интеллект и виртуальную реальность ',
          subName: '5',
          icons: 'image10.png'
        },
        {
          name: 'Читать и управлять кодом',
          subName: '5',
          icons: 'image10.png'
        },
        {
          name: 'Работать с компьютером в игровой форме',
          subName: '5',
          icons: 'image10.png'
        },
        {
          name: 'С лёгкостью осваивать английский язык',
          subName: '5',
          icons: 'image10.png'
        }
      ]
    }
  }
}
</script>

<style>
.agile__dot {
  margin: 10px 6px;
}
.agile__dot button {
  background-color: #eee;
  border: none;
  border-radius: 50%;
  cursor: pointer;
  display: block;
  height: 10px;
  font-size: 0;
  line-height: 0;
  margin: 0;
  padding: 0;
  transition-duration: 0.3s;
  width: 10px;
}

.agile__actions {
  justify-content: center !important;
  align-items: baseline;
  gap: 8px;
}
.agile__dot--current button,
.agile__dot:hover button {
  background-color: #a754f7;
}
</style>
