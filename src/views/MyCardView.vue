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
  },
  {
    ruby: '今日は風が少し騒がしいな',
    base: '今天的風兒有點喧囂啊',
    info: ['https://www.youtube.com/watch?v=fQr4mrSE_hE', '男子高校生の日常']
  }
])

const randomGreeting = ref()
const getRandomGreeting = () => {
  const randomIndex = Math.floor(Math.random() * greetings.value.length)
  randomGreeting.value = greetings.value[randomIndex]
  randomGreeting.value = greetings.value[2]
}
getRandomGreeting()
</script>

<template>
  <div
    class="mx-auto flex aspect-[14/23] flex-col justify-between overflow-auto border border-gray-300"
  >
    <div class="flex w-full flex-col items-center justify-between pt-3">
      <img
        src="https://avatars.githubusercontent.com/u/21689326?s=400&u=3659405c346f21ac9c082fbf72c3d18626e1c4d0&v=4"
        alt=""
        class="mt-3 h-32 w-32 rounded-full"
      />
      <h2 class="my-3 text-3xl font-semibold">Webb Lu</h2>
      <address>
        <div class="flex flex-col items-center space-y-2">
          <a href="https://github.com" target="_blank" class="text-blue-500">GitHub</a>
          <a href="https://telegram.org" target="_blank" class="text-blue-500">Telegram</a>
          <a href="https://discord.com" target="_blank" class="text-blue-500">Discord</a>
        </div>
      </address>
    </div>

    <div class="flex w-full items-center justify-center p-4">
      <div class="w-full whitespace-pre-wrap text-center text-3xl">
        <ruby
          >{{ randomGreeting.base }}
          <rp>)</rp>
          <rt>{{ randomGreeting.ruby }}</rt>
          <rp>(</rp>
        </ruby>
        <button @click="getRandomGreeting">🔄</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.greeting {
  color: red;
  font-weight: bold;
}
</style>
