<script setup>
import { ref } from 'vue'
// const greeting = ref('Hello World!')
const greetings = ref([
  {
    ruby: 'Hello, World!',
    base: '你好，世界！'
  },
  {
    ruby: '君には興味がない、私には才能がない',
    base: '你沒有興趣，而我沒有才能'
  },
  {
    ruby: '昔はお前みたいな冒険者だったんだがなぁ、膝に矢を受けてしまって',
    base: '我以前也是像你這樣的冒險家，直到我的膝蓋中了一箭'
  },
  {
    ruby: 'すべてはシュタインズゲートの選択だ',
    base: '一切都是命運石之門的選擇'
  },
  {
    ruby: '最新の魔法を見せてあげる',
    base: '讓你看看最新的魔法',
    info: ['https://www.youtube.com/watch?v=sJ6KbVtzN5g']
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
  <p class="text-3xl font-bold underline">
    <ruby
      >{{ randomGreeting.base }}
      <rp>)</rp>
      <rt>{{ randomGreeting.ruby }}</rt>
      <rp>(</rp>
    </ruby>
    <button @click="getRandomGreeting">🔄</button>
  </p>
  <p>Webb Lu</p>
  <address>
    <small> [Discord] [GitHub] [Mail] [Telegram] </small>
  </address>
</template>

<style scoped>
.greeting {
  color: red;
  font-weight: bold;
}
</style>
