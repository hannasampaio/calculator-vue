<script setup>
    const props = defineProps(['resultado']);
</script>

<template>
    <div v-if="props.resultado !== null" class="alert alert-info text-center mt-4">
        <strong>Resultado:</strong> {{ props.resultado }}
    </div>
</template>

<style scoped>
    .alert {
        font-size: 1.5rem;
    }
</style>
