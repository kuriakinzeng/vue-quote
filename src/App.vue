<template>
    <div class="container">
        <AppHeader :quoteCount="quotes.length" :maxQuotes="maxQuotes"></AppHeader>
        <NewQuote @quoteAdded="newQuote"></NewQuote>
        <QuoteGrid :quotes="quotes" @quoteDeleted="deleteQuote"></QuoteGrid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info"><strong>Info:</strong> Click on a quote to delete it.</div>
            </div>
        </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue';
    import NewQuote from './components/NewQuote.vue';
    import AppHeader from './components/Header.vue';
    export default {
        data: () => ({
            quotes: ['Lorem ipsum'],
            maxQuotes: 10
        }),
        methods: {
            newQuote(quote){
                if (this.quotes.length >= this.maxQuotes)
                    return alert('You have reached max number of quotes');
                this.quotes.push(quote);

            },
            deleteQuote(index){
                this.quotes.splice(index,1);
            }
        },
        components: {
            QuoteGrid,
            NewQuote,
            AppHeader
        }
    }
</script>

<style>
</style>
