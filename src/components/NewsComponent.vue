<script setup>
import { onMounted, reactive } from "@vue/runtime-core";
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Autoplay, Navigation } from "swiper";
import "swiper/css/navigation";
// Import Swiper styles
import 'swiper/css';

//heroicons
import { ChevronLeftIcon, ChevronRightIcon } from "@heroicons/vue/24/solid";

const modules = reactive([Autoplay, Navigation])

const prop = defineProps({
    news: Array
})

onMounted(() => {
    Swiper, SwiperSlide
    // prop
    prop, modules
    // console.log(prop.news);
    ChevronLeftIcon, ChevronRightIcon
})
</script>
<template>
    <div class="w-full relative bg-gradient-to-r from-slate-500 to-slate-50 rounded-lg py-3 px-0">
        <swiper 
        :slides-per-view="1" 
        :space-between="50" 
        :loop="true" 
        class="w-4/5"
        :autoplay="true"
        :navigation="{
            nextEl: '.left',
            prevEl: '.right',
        }"
        :modules="modules">
            <swiper-slide v-for="notizia in prop.news" :key="notizia.id" class=" text-base text-slate-100 font-serif">
                {{ notizia.title }}
            </swiper-slide>
        </swiper>
        <div class="grid grid-cols-5 w-full justify-items-stretch absolute top-2.5 left-0 px-4">
            <ChevronLeftIcon class="w-7 h-7 left cursor-pointer" />
            <div class="col-span-3"></div>
            <ChevronRightIcon class="w-7 h-7 right justify-self-end cursor-pointer" />
        </div>

    </div>
</template>

<style scoped>
/* .swiper-button-prev {
    margin-left: -3rem;
} */
</style>