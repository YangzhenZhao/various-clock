<template>
  <div>
    <div class="show-time">{{ showDatetime }}</div>
  </div>
</template>

<script>
import { ref } from 'vue'
import * as dayjs from 'dayjs'
export default {
  name: 'Clock',
  setup () {
    const getShowDatetime = () => {
      const nowDatetime = dayjs()
      const hour = nowDatetime.hour().toString().padStart(2, '0')
      const minute = nowDatetime.minute().toString().padStart(2, '0')
      const second = nowDatetime.second().toString().padStart(2, '0')
      return `${hour} : ${minute} : ${second}`
    }
    const showDatetime = ref(getShowDatetime())
    const updateShowDatetime = () => {
      showDatetime.value = getShowDatetime()
    }
    setInterval(updateShowDatetime, 500)
    return {
      showDatetime
    }
  }
}
</script>

<style>
  .show-time {
    font-size: 3em;
    margin-top: 1em;
  }
</style>
