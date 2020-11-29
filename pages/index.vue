<template>
  <div class="w-screen h-screen content-center justify-center flex flex-col">
      <h1 class="text-center text-5xl md:text-6xl text-red-600">Daniela & Ján</h1>
      <h2 class="text-center text-3xl md:text-4xl text-red-500 mb-6">♥ 29.05.2021 ♥</h2>
      <div class="flex justify-center">
        <CountDown />
      </div>
  </div>
</template>

<script>
import CountDown from '@/components/CountDown'
export default {
  components: { CountDown }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

</style>
