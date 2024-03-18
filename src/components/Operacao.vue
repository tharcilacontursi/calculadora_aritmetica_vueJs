<script setup>
    const props = defineProps (['operacao','num1', 'num2'])

</script>

<template>
    <div class="operation">
        <h2>Selecione a operação que deseja:</h2>
        <select @change="props.operacao">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
        </select>
    </div>
    <div>
        <input @keyup="props.num1" type="number" required placeholder="Insira um número"/>
        <input @keyup="props.num2" type="number" required placeholder="Insira segundo número"/>

    </div>
</template>

<style scoped>
    input{
        margin: 30px;
        padding: 4px;
        border-radius: 4px;
    }
</style>