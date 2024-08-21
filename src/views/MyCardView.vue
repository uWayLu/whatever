<script setup>
import { ref } from 'vue'
const greeting = ref('Hello World!')
const greetings = ref([
    {
        base: '君には興味がない、私には才能がない',
        ruby: '你沒有興趣，而我沒有才能',
    },
    {
        base: '昔はお前みたいな冒険者だったんだがなぁ、膝に矢を受けてしまって',
        ruby: '我以前也是像你這樣的冒險家，直到我的膝蓋中了一箭'
    }
])

const randomGreeting = ref()
const getRandomGreeting = () => {
    const randomIndex = Math.floor(Math.random() * greetings.value.length)
    randomGreeting.value = greetings.value[randomIndex]
}
getRandomGreeting()
</script>

<template>
    <p class="greeting">
        <ruby>{{ randomGreeting.ruby }}
            <rp>)</rp>
            <rt>{{ randomGreeting.base }}</rt>
            <rp>(</rp>
        </ruby>
        <button @click="getRandomGreeting">🔄</button>
    </p>
    <p>Webb Lu</p>
    <address>
        <small>
            [Discord] [GitHub] [Mail] [Telegram]
        </small>
    </address>
</template>

<style scoped>
.greeting {
    color: red;
    font-weight: bold;
}
</style>
