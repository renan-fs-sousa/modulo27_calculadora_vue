<script setup>
    const props = defineProps(['resultado']);
</script>

<template>
    <div class="row py-5">
        <h2>Resultado: {{ props.resultado }}</h2>
    </div>
</template>