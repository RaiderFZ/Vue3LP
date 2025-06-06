<script setup lang="ts">
    import { ref } from 'vue';
    import {defineProps} from 'vue'
    
const props = defineProps<{send: string}>();

    const newCount = ref(0);

</script>

<template>

    <div>
        <p>{{ props.send }}</p>

        <p>Счетчик - {{ newCount }}</p>

        <button @click="newCount++">+</button>

        <button @click="newCount--">-</button>


    </div>
</template>

<style>

</style>