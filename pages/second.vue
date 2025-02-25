<script setup lang="ts">
import { ref } from 'vue'; // 'ref' Vue'den import edildi
import { VueFinalModal } from 'vue-final-modal';
import { UButton } from '#components'; // UButton bileşenini doğru şekilde import edin

const display2 = ref(false);
function toggleModal() {
    display2.value = !display2.value;
}
</script>

<template>
  <UButton @click="toggleModal" color="amber">VueFinal Modal</UButton>
  <VueFinalModal v-model="display2">
    <div class="bg-white p-20 rounded-xl w-[80%] h-[70vh] !z-0 flex items-center justify-center absolute"
      style="left: 50%; top: 50%; transform: translate(-50%, -50%);">
      <UButton @click="toggleModal" color="amber">Kapat</UButton> <!-- 'Kapat' butonuna click event'i eklendi -->
    </div>
  </VueFinalModal>
</template>
