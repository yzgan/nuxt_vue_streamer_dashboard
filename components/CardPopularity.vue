<template>
  <Card title="Popularity">
    <template v-slot:content>
      <div class="text-xs-center">
        <h1 class="my-3">{{ formattedSubscriberCount }}</h1>

        <v-sheet color="rgba(0, 0, 0, .12)" class="mb-3">
          <v-sparkline
            :value="value"
            color="rgba(255, 255, 255, .7)"
            height="100"
            padding="24"
            stroke-linecap="round"
            smooth
          >
            <template v-slot:label="item">
              {{ item.value }}
            </template>
          </v-sparkline>
        </v-sheet>

        <div class="subheading grey--text text--lighter-1">
          {{ subscribers.today }} Subscribed Today
        </div>
      </div>
    </template>
  </Card>
</template>

<script>
import Card from '@/components/Card'
const numeral = require('numeral')

export default {
  components: {
    Card
  },
  props: {},
  data: () => ({
    value: [423, 446, 675, 510, 590, 610, 760],
    subscribers: {
      total: 105032,
      today: 98
    }
  }),
  computed: {
    formattedSubscriberCount() {
      return numeral(this.subscribers.total).format('0,0')
    }
  }
}
</script>
