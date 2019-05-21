<template>
  <Card :title="source">
    <template v-slot:content>
      <v-list three-line>
        <template v-for="post in posts">
          <v-list-tile :key="post.avatar" avatar>
            <v-list-tile-avatar>
              <img :src="post.avatar" />
            </v-list-tile-avatar>
            <v-list-tile-content>
              <v-list-tile-title>
                {{ post.username }}
              </v-list-tile-title>
              <v-list-tile-sub-title>
                {{ post.comment }}
              </v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </template>

    <template v-slot:action>
      <v-layout align-content-center>
        <v-flex xs12>
          <div class="text-xs-center">{{ getTime() }}</div>
        </v-flex>
      </v-layout>
    </template>
  </Card>
</template>

<script>
import Card from '@/components/Card'
const moment = require('moment')

export default {
  components: {
    Card
  },
  props: {
    source: {
      default: 'Social media source',
      require: true,
      type: String
    }
  },
  data: () => ({
    updated: '2019-05-21T13:51:50.417+08:00',
    posts: [
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
        username: 'Ali Connors',
        comment:
          "I'll be in your neighborhood doing errands this weekend. Do you want to hang out?"
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
        username: 'Alex',
        comment: "Wish I could come, but I'm out of town this weekend."
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
        username: 'Sandra Adams',
        comment: "Wish I could come, but I'm out of town this weekend. x2"
      }
    ]
  }),
  methods: {
    getTime() {
      return 'Latest updated ' + moment(this.updated).fromNow()
    }
  }
}
</script>
