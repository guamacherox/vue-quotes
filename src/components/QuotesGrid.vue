<template lang="html">
  <div class="row">
    <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{quote}}</app-quote>
  </div>
</template>

<script>

import Quote from './Quote.vue'

export default {
  props: ['quotes'],
  data() {
    return {};
  },
  components: {
    'app-quote': Quote
  },
  methods:{
    deleteQuote(index) {
      this.$emit('onDeleteQuote', index);      
    }
  }
}
</script>

<style lang="css">

</style>
