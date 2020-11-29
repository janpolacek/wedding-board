<template>
  <div class="flex items-center space-x-2 sm:space-x-4">
    <number :number="clock.days" label="Dní"/>
    <number :number="clock.hours" label="Hodín"/>
    <number :number="clock.minutes" label="Minút"/>
    <number :number="clock.seconds" label="Sekúnd"/>
  </div>
</template>

<script>

import Number from '@/components/Number'
export default {
  components: { Number },
  data: () => {
    return {
      clock: {
        days: '00',
        hours: '00',
        minutes: '00',
        seconds: '00',
        remaining: 1000
      },
      deadline: '29 May 2021'
    }
  },
  created () {
    this.clock = this.calculateTimeLeft()
    this.startCountdown()
  },

  methods: {
    startCountdown () {
      const countdownIntervalFunction = setInterval(() => {
        const timeLeft = this.calculateTimeLeft()
        this.clock = timeLeft
        if (timeLeft.remaining <= 0) {
          clearInterval(countdownIntervalFunction)
        }
      }, 1000)
    },
    calculateTimeLeft () {
      const remaining = Date.parse(this.deadline) - Date.parse(new Date())
      const seconds = Math.floor((remaining / 1000) % 60)
      const minutes = Math.floor((remaining / 1000 / 60) % 60)
      const hours = Math.floor((remaining / (1000 * 60 * 60)) % 24)
      const days = Math.floor(remaining / (1000 * 60 * 60 * 24))
      return {
        days,
        hours,
        minutes,
        seconds,
        remaining
      }
    }
  }
}
</script>
