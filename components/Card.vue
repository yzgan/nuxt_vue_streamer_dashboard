<template>
  <v-flex xs12 sm6 md3 d-flex px-3>
    <v-card dark darken-3>
      <v-card-title primary-title>
        <div>
          <h3 class="title mb-0 orange--text">{{ upcasedTitle }}</h3>
        </div>
      </v-card-title>
      <v-divider></v-divider>
      <v-card-text class="card-content">
        <slot name="content">
          {{ description }}
        </slot>
      </v-card-text>
      <v-card-actions class="card-action" pt-3>
        <slot name="action">
          <!-- <v-layout>
            <v-flex>
              <v-btn flat color="orange">Share</v-btn>
              <v-btn flat color="orange">Explore</v-btn>
            </v-flex>
          </v-layout> -->
        </slot>
      </v-card-actions>
    </v-card>
  </v-flex>
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: {
      type: String,
      require: true,
      default: 'Card Title'
    },
    description: {
      type: String,
      default: 'Card Description'
    }
  },
  computed: {
    upcasedTitle: function() {
      return this.title.toUpperCase()
    }
  }
}
</script>

<style scoped>
.card-content {
  height: 300px;
  overflow: auto;
}

.card-action {
  position: relative;
  bottom: 0;
  min-height: 4em;
}
</style>
