<template>
    <div class="row">
      <form>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
          <input type="text" placeholder="New quote..." class="form-control" v-model="quote"></input>
        </div>
        <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
          <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
        </div>
      </form>
    </div>
</template>

<script>
  export default {
    data: function() {
      return {
        quote: ''
      }
    },
    methods: {
      createNew() {
        this.$emit('quoteAdded', this.quote);
        this.quote = '';
      }
    }
  }
</script>

<style>
</style>
