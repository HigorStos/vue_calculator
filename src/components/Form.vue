<script setup>
    const props = defineProps(['numA', 'numB', 'operation'])
</script>

<template>
    <form class="d-flex flex-column ms-auto me-auto mt-4 mb-4 w-50">
      <input @change="props.numA" @keyup="props.numA" class="mb-3 ps-2" type="number" placeholder="Primeiro número" min="0" required>
      <input @change="props.numB" @keyup="props.numB" class="mb-3 ps-2" type="number" placeholder="Segundo número" min="0" required>
      <select @change="props.operation" class="p-1">
        <option value="adicao">Adição</option>
        <option value="subtracao">Subtração</option>
        <option value="multiplicacao">Multiplicação</option>
        <option value="divisao">Divisão</option>
      </select>
    </form>
</template>