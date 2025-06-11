<script setup lang="ts">
    import { computed, reactive, ref, watch } from 'vue';

    type Item = {
        name: string
        qty: number
    }

    const items = ref<Item[]>([]);
    const name = ref('');
    const qty = ref(1);

    const addItem = () => {
        if(name.value.trim() && qty.value > 0) {
            items.value.push({name: name.value, qty: qty.value})
            name.value = '';
            qty.value = 1
        }
    }

    const removeItem = (index: number) => {
        items.value.splice(index, 1);
    }

    const totalPrice = computed(() => 
        items.value.reduce((sum, item) => sum + item.qty, 0)
    );


</script>

<template>
    <div>
        <h2>Список покупок</h2>
        <input v-model="name" type="text" placeholder="Товар">
        <input v-model="qty" type="number" placeholder="Количество">
        <button @click="addItem">Добавить</button>

        <ul>
            <li v-for="(item, index) in items" :key='index'>
                {{ item.name }} - {{ item.qty }} 
                
                <button @click="removeItem(index)">
                    Удалить
                </button>
            </li>
        </ul>

        <p>Общее количество товаров: {{ totalPrice }}</p>
    </div>
</template>

<style>
    input {
        margin: 4px;
        padding: 4px;
    }

    button {
        margin-left: 6px;
    }

    li {
        margin: 8px 0;
        list-style: none;
    }
</style>