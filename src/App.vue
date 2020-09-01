<template>
    <div class="container">
        <Header :max-quotes="maxQuotes" :quote-count="quotes.length"></Header>
        <new-quote @newQuoteCreated="handleNewQuoteCreated"></new-quote>
        <quote-grid :quotes="quotes" @deleteQuote="handleQuoteDeletion"></quote-grid>
        <div class="row">
            <div class="col-sm-12 text-center">
                <div class="alert alert-info">
                    Info: Click on a quote to delete it.
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import QuoteGrid from "@/components/QuoteGrid";
import NewQuote from "@/components/NewQuote";
import Header from "@/components/Header";

export default {
    name: 'App',
    components: {Header, NewQuote, QuoteGrid},
    data: () => ({
        quotes: ['Quote 1'],
        maxQuotes: 10
    }),
    methods: {
        handleNewQuoteCreated(newQuoteText) {
            this.quotes.push(newQuoteText);
        },
        handleQuoteDeletion(index) {
            this.quotes.splice(index, 1);
        },
    }

}
</script>

<style>
</style>
