<script setup>
    const props = defineProps(['isCalculated', 'result', 'getNum1', 'getNum2']);
</script>

<template>
    <div class="inputs centered">
        <input @change="props.getNum1" type="number" placeholder="Number">
        <input @change="props.getNum2" type="number" placeholder="Number">
    </div>
</template>