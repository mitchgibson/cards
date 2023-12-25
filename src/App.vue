<script setup lang="ts">
import { ref } from 'vue';

const active = ref('1');
const cards = ref([
  {
    id: '1',
    image: "bg-[url('./assets/1.jpg')]",
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ornare massa nec libero ullamcorper porttitor. Integer auctor."
  },
  {
    id: '2',
    image: "bg-[url('./assets/2.jpg')]",
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ornare massa nec libero ullamcorper porttitor. Integer auctor."
  },
  {
    id: '3',
    image: "bg-[url('./assets/3.jpg')]",
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ornare massa nec libero ullamcorper porttitor. Integer auctor."
  },
  {
    id: '4',
    image: "bg-[url('./assets/4.jpg')]",
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ornare massa nec libero ullamcorper porttitor. Integer auctor."
  },
  {
    id: '5',
    image: "bg-[url('./assets/5.jpg')]",
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ornare massa nec libero ullamcorper porttitor. Integer auctor."
  },
  {
    id: '6',
    image: "bg-[url('./assets/6.jpg')]",
    text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque ornare massa nec libero ullamcorper porttitor. Integer auctor."
  }
]);

function toggleCard(id:string) {
  // active.value = active.value === id ? '' : id;
  active.value = id;
}


</script>

<template>
  <div class="w-screen h-screen bg-stone-50">
    <div class="flex flex-col items-center justify-center h-full">
        <div class="flex flex-row items-center justify-center w-full h-full">
          <div v-for="card in cards" @click="toggleCard(card.id)" :class="[{'w-96': active === card.id, 'hover:scale-105': active !== card.id}, card.image]" 
          class="w-16 h-64 mr-2 overflow-hidden duration-1000 bg-black bg-cover rounded-xl transition-width">
          
          <div class="flex flex-col items-start justify-end h-full">
            <div class="p-6 grow">
              <p v-if="card.text" :class="{'scale-100 duration-700 delay-700': active === card.id, 'scale-0': active !== card.id}" class="p-2 transition-all rounded-lg opacity-60 bg-neutral-900 text-neutral-200">{{ card.text }}</p>
            </div>
            <button :disabled="active === card.id" class="flex items-center justify-center flex-none w-10 h-10 mx-3 mb-2 rounded-full opacity-60 bg-neutral-900 text-neutral-200">{{ card.id }}</button>
          </div>
          </div>
        </div>
    </div>
  </div>  
</template>

<style scoped>

</style>
