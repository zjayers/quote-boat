<template>
    <div class="row">
        <quote v-for="(quote, index) in quotes" :key="quote" @click.native="emitDeleteQuoteEvent(index)">{{
                quote
            }}
        </quote>
    </div>
</template>

<script>
import Quote from "@/components/Quote";

export default {
    name: "QuoteGrid",
    components: {Quote},
    props: ['quotes'],
    methods: {
        emitDeleteQuoteEvent(index) {
            this.$emit('deleteQuote', index)
        }
    }
}
</script>

<style scoped>

</style>
