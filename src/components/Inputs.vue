<script setup>
const props = defineProps(['isCalculated', 'result', 'getNum1', 'getNum2', 'num1', 'num2']);
</script>

<template>
    <div class="inputs centered">
        <input :value="num1" @change="props.getNum1" type="number" placeholder="Number">
        <input :value="num2" @change="props.getNum2" type="number" placeholder="Number">
    </div>
</template>