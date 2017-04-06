<template>
  <div class="row">

    <!-- Native modifier allows us to interact with components on the template -->
    <app-quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</app-quote>

  </div>
</template>



<script>
  import Quote from './Quote.vue';
  export default {
    props: ['quotes'],
    components: {
      appQuote: Quote
    },
    methods: {
      deleteQuote(index) {
        this.$emit('quoteDeleted', index);
      }
    }
  }
</script>



<style>

</style>
