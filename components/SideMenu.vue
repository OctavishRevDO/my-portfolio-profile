<script setup>
const props = defineProps({
    menus: {
        type: Object,
        required: true
    },
})
const { menus } = props

const isOpen = ref(false)
</script>

<template>
  <div>
    <button
          type="button"
          class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700"
          @click="isOpen = true" 
        >
          <span class="w-10 h-10 flex justify-center items-center rounded-full text-gray-400 hover:text-white transition-all pointer-events-auto"><UIcon name="i-heroicons-ellipsis-vertical-16-solid" /></span>
        </button>

    <USlideover v-model="isOpen" prevent-close>
        <UCard class="flex flex-col flex-1" :ui="{ body: { base: 'flex-1' }, ring: '', divide: 'divide-y divide-gray-100 dark:divide-gray-800' }">
          <template #header>
            <div class="flex items-center justify-between">
              <h3 class="text-base font-semibold leading-6 text-gray-900 dark:text-white">
                Slideover
              </h3>
              <UButton color="gray" variant="ghost" icon="i-heroicons-x-mark-20-solid" class="-my-1" @click="isOpen = false" />
            </div>
          </template>
  
          <div class="h-full">
            <div v-for="menu in menus" :key="menu.id">
                <p>{{menu.name}}</p>
            </div>
          </div>
        </UCard>
      </USlideover>
    </div>
  </template>