<template>
    <div class="row">
        <Quote v-for="(quote, index) in quotes" @click.native="deleteQuote(index)">{{ quote }}</Quote>
    </div>
</template>

<script>
    import Quote from './Quote.vue';
    export default {
        props: ['quotes'],
        methods: {
          deleteQuote(index) {
            this.$emit('quoteDeleted',index);
          }
        },
        components: {
          Quote
        }
    }
</script>

<style>
</style>
