<template>
  <Card title="User Profile">
    <template v-slot:content>
      <div class="text-xs-center">
        <div>
          <v-avatar size="100">
            <img :src="imageUrl" alt="avatar" />
          </v-avatar>
        </div>
        <div class="my-4">
          <p class="title">{{ name }}</p>
          <p class="subheading grey--text text--lighter-1">
            {{ description }}
          </p>
        </div>
        <div id="links">
          <v-layout justify-space-around>
            <span class="group pa-2">
              <v-btn fab small>
                <v-icon>mdi-android</v-icon>
              </v-btn>
              <v-btn fab small>
                <v-icon>mdi-wrench</v-icon>
              </v-btn>
              <v-btn fab small>
                <v-icon>mdi-run</v-icon>
              </v-btn>
              <v-btn fab small>
                <v-icon>mdi-space-invaders</v-icon>
              </v-btn>
            </span>
          </v-layout>
        </div>
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
  props: {
    name: {
      type: String,
      require: true,
      default: 'Who am i?'
    },
    // eslint-disable-next-line
    description: {
      type: String
    },
    imageUrl: {
      type: String,
      default:
        'https://gravatar.com/avatar/8300278a2a2e802e749e2c960648b267?s=200&d=robohash&r=x'
    }
  }
}
</script>
