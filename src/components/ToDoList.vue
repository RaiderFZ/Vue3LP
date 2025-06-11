<script setup lang="ts">
    import { ref } from 'vue';

    type Tasks = string[]

    const list = ref<Tasks>([]);
    const task = ref("");

    const addTask = () => {
        if(task.value.trim()) {
            list.value.push(task.value)
            task.value = '';
        }
    }

    const removeTask = (i: number) => {
        list.value.splice(i, 1);
    }
</script>

<template>
    <div>
        <h2>Списсок дел</h2>
        <input v-model="task" placeholder="Новая задача" type="text">
        <button @click="addTask">Добавить</button>

        <ul>
            <li v-for="(item, index) in list" :key="index">
                {{ item }} <button @click="removeTask(index)">
                    удалить
                </button>
            </li>
        </ul>
    </div>
</template>

<style>
    input {
        margin-right: 8px;
        padding: 4px;
    }

    button {
        margin-left: 8px;
        cursor: pointer;
    }

    ul {
        padding-left: 0;
    }

    li {
        list-style: none;
        margin: 6px 0;
    }
</style>
