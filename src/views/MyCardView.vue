<script setup>
import { ref } from 'vue';
const greeting = ref('Hello World!')
</script>

<template>
    <p class="greeting">{{ greeting }}</p>
</template>


<style scoped>
.greeting {
    color: red;
    font-weight: bold;
}
</style>