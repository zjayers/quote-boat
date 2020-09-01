<template>
    <div class="row">
        <form>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <label for="quote-input">Quote</label>
                <textarea id="quote-input" v-model="quote" class="form-control" cols="30" name="quote-input"
                          rows="3"></textarea>
            </div>
            <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
                <button :disabled="buttonDisabled" class="btn btn-primary" @click.prevent="emitQuoteCreationEvent">
                    Create New Quote
                </button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    name: "NewQuote",
    data: () => ({
        quote: ''
    }),
    methods: {
        emitQuoteCreationEvent() {
            if (this.quote === '') return;
            this.$emit('newQuoteCreated', this.quote);
            this.quote = '';
        }
    },
    computed: {
        buttonDisabled: function () {
            return this.quote === '';
        }
    }
}
</script>

<style scoped>

</style>
