<script setup>
import '@/assets/main.css'

defineProps({
    resources: {
        type: Array,
        required: true
    },
    descriptions: {
        type: Array,
        required: true
    }
})
</script>
<template>
    <ul>
        <button v-for="(resource, description, index) in resources" :key="index" 
        class="bg-[var(--blue)] flex flex-col gap-2 items-center justify-center rounded-md hover:bg-[var(--gold)] hover:scale-105 transition-all duration-200 cursor-pointer"
        @click="navigateTo(`/street-tips/${resource}`)">
            <h3 class="text-center text-white px-2">{{ resource }}</h3>
            <p class="text-center text-white px-2">{{ description }}</p>
        </button>
    </ul>
</template>