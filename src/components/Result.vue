<script setup>
    const props = defineProps(['resultado'])
</script>

<template>
    <div class="text-center text-white bg-primary rounded mt-4 p-4">
        <h3>Resultado:</h3>
        <h3> {{ props.resultado }} </h3>
    </div>
</template>