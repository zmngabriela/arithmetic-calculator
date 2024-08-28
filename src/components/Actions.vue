<script setup>
    const props = defineProps(['setOperator', 'restart']);
</script>

<template>
    <div class="actions centered">
        <select @change="props.setOperator">
            <option value="">Operator</option>
            <option value="addition">Addition</option>
            <option value="subtraction">Subtraction</option>
            <option value="division">Division</option>
            <option value="multiplication">Multiplication</option>
        </select>
        <button @click="props.restart">
            <img src="../components/icon/restart.png" alt="Restart">
        </button>
    </div>
</template>