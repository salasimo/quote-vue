<template>
    <div class="row">
        <cmp-quote
            v-for="(quote, index) in quotesProp"
            @click.native="deleteQuote(index)"
            >{{ quote }}</cmp-quote
        >
    </div>
</template>

<script>
import Quote from "./Quote.vue";
export default {
    props: ["quotesProp"],
    components: {
        "cmp-quote": Quote,
    },
    methods: {
        deleteQuote(index) {
            this.$emit("quoteDeleted", index);
        },
    },
};
</script>

<style scoped></style>
