<template>
  <Card title="post message">
    <template v-slot:content>
      <v-form ref="form" v-model="post">
        <v-layout row wrap>
          <v-flex xs12>
            <v-textarea
              v-model="message"
              name="message"
              label="Message"
              hint="Message will be posted to all live social media"
              outline
            ></v-textarea>
          </v-flex>
        </v-layout>
      </v-form>
      <v-layout row wrap align-center grid-list-md text-xs-center>
        <v-flex xs6>
          <div>
            Facebook
          </div>
        </v-flex>
        <v-flex xs6>
          <Loading
            :loading="facebook.isLoading"
            :success="facebook.isSuccess"
          />
        </v-flex>
        <v-flex xs6>
          <div>
            YouTube
          </div>
        </v-flex>
        <v-flex xs6>
          <Loading :loading="youtube.isLoading" :success="youtube.isSuccess" />
        </v-flex>
        <v-flex xs6>
          <div>
            Twitch
          </div>
        </v-flex>
        <v-flex xs6>
          <Loading :loading="twitch.isLoading" :success="twitch.isSuccess" />
        </v-flex>
      </v-layout>
    </template>
    <template v-slot:action>
      <v-container grid-list-xs>
        <v-layout row wrap>
          <v-flex d-flex>
            <v-btn round> Send </v-btn>
          </v-flex>
        </v-layout>
      </v-container>
    </template>
  </Card>
</template>

<script>
import Card from '@/components/Card'
import Loading from '@/components/Loading'

export default {
  components: {
    Card,
    Loading
  },
  data: () => ({
    post: false,
    message: '',
    facebook: {
      isLoading: false,
      isSuccess: false
    },
    youtube: {
      isLoading: true,
      isSuccess: false
    },
    twitch: {
      isLoading: false,
      isSuccess: true
    }
  })
}
</script>
