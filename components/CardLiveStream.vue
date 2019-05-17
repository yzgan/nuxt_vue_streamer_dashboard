<template>
  <Card title="live stream">
    <template v-slot:content>
      <div class="text-xs-center">
        <v-layout
          v-for="stream in streams"
          :key="stream.index"
          row
          wrap
          align-center
        >
          <v-flex xs6>
            <v-hover>
              <v-btn
                slot-scope="{ hover }"
                :class="`${hover ? stream.color : null}`"
                flat
              >
                <v-icon> {{ stream.icon }} </v-icon>
              </v-btn>
            </v-hover>
          </v-flex>
          <v-flex xs6>
            <v-btn small :class="isLive(stream)">
              Live
            </v-btn>
          </v-flex>
        </v-layout>
      </div>
    </template>
  </Card>
</template>

<script>
import Card from '@/components/Card'

export default {
  components: {
    Card
  },
  data: () => ({
    streams: [
      { icon: 'mdi-facebook', status: 'live', color: 'indigo' },
      { icon: 'mdi-youtube', status: null, color: 'red' },
      { icon: 'mdi-twitch', status: 'live', color: 'deep-purple' }
    ]
  }),
  methods: {
    isLive: stream => (stream.status === 'live' ? 'red' : null)
  }
}
</script>
