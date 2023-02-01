<script setup>
import { onMounted } from "@vue/runtime-core";

const prop = defineProps({
    item: Object
})

onMounted(() => {
    prop
})

// onMounted
</script>
<template>

    <div class="w-full rounded-md border-slate-100 border-solid border relative bg-gradient-to-r from-slate-500 to-transparent p-5">  
        <div class="absolute bg-slate-300 -mt-8 px-3 rounded-lg -ml-2">
            <span class=" text-xs">
                {{ prop.item.category }}
            </span>
        </div>
        <div class="grid grid-cols-3 gap-x-5 w-full">
            <div class="col-span-2">
                <p class="text-sm text-slate-100 font-serif">
                    {{ prop.item.title }}   
                </p>
                <div class="flex mt-5">
                    <span class=" text-xs font-thin">
                        {{ prop.item.date }}
                    </span>
                </div>     
            </div>
            <img :src="prop.item.src" class=" rounded-md object-cover h-16 w-full" alt="">

        </div>
    </div>
    
</template>