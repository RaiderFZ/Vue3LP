<script setup>
 import { onBeforeMount, onMounted, onBeforeUpdate, onUpdated, onBeforeUnmount, onUnmounted, ref  } from 'vue';

 const str = ref(0);

    onBeforeMount(() => {
        console.log('Перед монтированием Dom');
        
        console.log(str.value)
    })

    onMounted(() => {
        console.log('Компонент Dom доступен');
        // const interval =setInterval(() => str.value++, 1000);
    })

    onBeforeUpdate(() => {
        console.log('Перед обновлением реактивных данных');
        
        console.log(str.value)
    })

    onUpdated(() => {
        console.log('После обновления')
        
        console.log(str.value)
    })
    onBeforeUnmount(() => {
         console.log('Перед удалением')
    })
   

    onUnmounted(() => {
        clearInterval(interval);
        console.log('Компонент уничтожен');
    });
</script>


<template>
    <div>
        <p>Метод жизненного цикла</p>
        <div>{{ str }}</div>
    </div>
</template>

<style>

</style>