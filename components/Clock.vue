<template>
  <Card title="Clock">
    <template v-slot:content>
      <div class="text-xs-center">
        <p class="display-2">{{ timeNow }}</p>
        <p class="title">{{ dateNow }}</p>
      </div>
    </template>
  </Card>
</template>

<script>
import Card from '~/components/Card'
import moment from 'moment'

export default {
  components: {
    Card
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
