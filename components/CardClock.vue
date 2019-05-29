<template>
  <Card title="Clock">
    <template v-slot:content>
      <div class="text-xs-center">
        <analog-clock height="200" width="200" />

        <p class="display-2">{{ timeNow }}</p>
        <p class="title">{{ dateNow }}</p>
      </div>
    </template>
  </Card>
</template>

<script>
import Card from '~/components/Card'
import moment from 'moment'
import AnalogClock from '~/components/AnalogClock'

export default {
  components: {
    Card,
    AnalogClock
  },
  data: () => ({
    ticker: null,
    timeNow: '-',
    dateNow: '-'
  }),
  computed: {},
  created() {
    this.ticker = setInterval(() => {
      this.timeNow = this.updateDateTime().format('LTS')
      this.dateNow = this.updateDateTime().format('LL')
    }, 1000)
  },
  destroyed() {
    clearInterval(this.ticker)
  },
  methods: {
    updateDateTime: () => moment(Date.now())
  }
}
</script>
