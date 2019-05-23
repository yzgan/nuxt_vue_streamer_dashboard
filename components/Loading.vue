<template>
  <div class="text-xs-center">
    <v-layout row wrap align-center>
      <v-flex xs-12>
        <v-progress-circular
          v-if="loading"
          :indeterminate="!success"
          :value="0"
          size="24"
          class="ml-2"
        ></v-progress-circular>
        <v-icon v-if="success" color="green" class="pl-2">
          mdi-check-bold
        </v-icon>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
export default {
  props: {
    loading: {
      type: Boolean,
      default: false,
      require: true
    },
    success: {
      type: Boolean,
      default: false,
      require: true
    }
  }
}
</script>
