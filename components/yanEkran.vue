<script setup lang="ts">
const isOpen = ref(false)

import type { FormError, FormSubmitEvent } from '#ui/types'

const state = reactive({
  email: undefined,
  password: undefined})



  const validate = (state: any): FormError[] => {
  const errors = []
  if (!state.email) errors.push({ path: 'email', message: 'Required' })
  if (!state.password) errors.push({ path: 'password', message: 'Required' })
  return errors
}

async function onSubmit(event: FormSubmitEvent<any>) {
  // Do something with data
  console.log(event.data)
}

</script>

<template>
  <div>
    <UButton label="Yan Pencere" @click="isOpen = true" />

    <USlideover v-model="isOpen" prevent-close >
        <div class="p-4 flex-1  text-white ">
            <button @click="isOpen = false">X</button>
            <UForm :state="state" class="space-y-4" @submit="onSubmit">
                <fieldset >
                    <legend class="text-red-500">E mail ve Şifre Girişi</legend>
                    <UFormGroup label="Email" name="email">
                    <UInput v-model="state.email" placeholder="E-mail"/>
                    </UFormGroup>

                    <UFormGroup label="Password" name="password">
                    <UInput v-model="state.password" type="password"  placeholder="Şifre"/>
                    </UFormGroup>
   
                    <UFormGroup label="Telefon" type="number" >
                        <fieldset >
                            <legend>3 tane telefon numarası</legend>
                            <UInput  type="number"  placeholder="Telefon"/><br>
                            <UInput  type="number"  placeholder="Telefon"/><br>
                            <UInput  type="number"  placeholder="Telefon"/><br>
                        </fieldset>
                    </UFormGroup>
                    <UButton type="submit">Submit</UButton>
                </fieldset>
            </UForm>
        </div>
    </USlideover>
  </div>
</template>

