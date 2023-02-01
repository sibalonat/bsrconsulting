<script setup>
import { onMounted, ref } from '@vue/runtime-core'
import CardsComponent from './components/CardsComponent.vue'
import NewsComponent from './components/NewsComponent.vue';
// NewsComponent

const items = ref([])
const news = ref([])

const itemsString = ref('')

onMounted(() => {
  items.value.push(
    {
      id: 1,
      category: 'Turismo',
      title: 'Vlora Marina, Il Progetto Più Importante Per Il Turismo Marittimo Del Paese',
      date: 'Tuesday January  3rd, 2023',
      src: './images/porto-turistico-valona-1.webp'
    },
    {
      id: 2,
      category: 'Video',
      title: "Made in Albania, Giornata di studio sul tema L'Albania di Skanderbeg in Italia",
      date: 'Tuesday January  3rd, 2023',
      src: './images/Made-in-Albania.webp'
    },
    {
      id: 3,
      category: 'Video',
      title: 'Conviene investire in Albania? La risposta di Italian Network',
      date: 'Tuesday January  3rd, 2023',
      src: './images/Laera-Intervista.webp'
    },
    {
      id: 4,
      category: 'Economia',
      title: "(Italiano) Promuovere l'integrazione ",
      date: 'Tuesday January  3rd, 2023',
      src: './images/Promuovere-lintegrazione-economica-nei-Balcani-occidentali.webp'
    },
  )
  news.value.push(
    {
      id: 1,
      title: "Conferenza Nazionale  “L'Italia e i Balcani Occidentali: crescita e integrazione” (Trieste, 24 gennaio 2023)"
    },
    {
      id: 2,
      title: "Informazione per avvocati italiani - Istanze gratuite patrocinio"
    },
    {
      id: 3,
      title: "Avviso esplorativo per vendita all'asta di un'autovettura"
    },
    {
      id: 4,
      title: "Avviso di indizione di gara"
    },
  )
  itemsString.value = items.value.length.toString()

  // components
  CardsComponent, NewsComponent
})

</script>

<template>
  <div class="mx-auto w-screen my-auto h-screen bg-slate-800">
    <div class="container mx-auto">
      <div class="w-full pt-28">
        <NewsComponent :news="news" />
      </div>

      <hr class="mt-5 w-10/12 mx-auto">

      <div class="grid content-center h-60 gap-x-8"
        :class="items > 4 ? 'grid-cols-4' : 'grid-cols-' + itemsString + ''">
        <CardsComponent v-for="item in items" :key="item.id" :item="item" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
