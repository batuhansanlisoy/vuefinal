<script setup lang="ts">
import { VueFinalModal } from 'vue-final-modal';

const display = ref(false);

function toggleModal() {
    display.value = !display.value;


}
</script>

<template>
<UButton @click="toggleModal" color="amber">VueFinal Modal</UButton>
<VueFinalModal
v-model="display"
:hide-overlay="true"
:click-to-close="false"
:esc-to-close="false"
class="!z-40" >
    <div class="bg-white p-20 rounded-xl  w-[80%] h-[70vh] flex items-center justify-center absolute " 
    style="left: 50%; top: 50%;transform: translate(-50%, -50%);">
    <div class="p-5">
        <h1 class="text-red-700">Başlık </h1>
        <span class="text-black"> deneme 1 2 4</span>
        <br><br>
        <UButton @click="toggleModal">KAPAT</UButton>
        <br><br>
        
        <div>
        <YanEkran></YanEkran>
        </div>
        </div>
        
       
    </div>
</VueFinalModal>
</template>