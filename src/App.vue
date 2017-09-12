<template>
    <div class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      <app-quotes-grid :quotes="quotes" @onDeleteQuote="deleteQuote"></app-quotes-grid>
      <div class="row">
        <div class="col-sm-12">
          <div class="alert alert-info text-center">Info: Click on a quote to delete it</div>
        </div>
      </div>
    </div>
</template>

<script>

import QuotesGrid from './components/QuotesGrid.vue'
import NewQuote from './components/NewQuote.vue'
import Header from './components/Header.vue'

    export default {
        data () {
          return {
            quotes: [
              'The initial  quote'
            ],
            maxQuotes: 10
          }
        },
        components: {
          'app-header': Header,
          'app-quotes-grid': QuotesGrid,
          'app-new-quote': NewQuote
        },
        methods: {
          newQuote(data) {
            if(this.quotes.length >= this.maxQuotes) {
              return alert("Please Delete Quotes");
            }
            this.quotes.push(data);
          },
          deleteQuote(index) {
            this.quotes.splice(index, 1);
          }
        }

    }
</script>

<style>
</style>
