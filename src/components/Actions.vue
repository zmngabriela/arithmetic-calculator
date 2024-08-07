<script setup>
    const props = defineProps(['setOperator', 'restart']);
</script>

<template>
    <div class="actions centered">
        <select @change="props.setOperator">
            <option value="">Operator</option>
            <option value="somar">Somar</option>
            <option value="subtrair">Subtrair</option>
            <option value="dividir">Dividir</option>
            <option value="multiplicar">Multiplicar</option>
        </select>
        <button @click="props.restart">
            <img src="../components/icon/restart.png" alt="Recomecar">
        </button>
    </div>
</template>