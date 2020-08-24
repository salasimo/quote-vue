<template>
    <div class="container">
        <header class="row">
            <h2>Citazioni aggiunte</h2>
            <cmp-header-bar
                :quoteCount="quotesData.length"
                :maxQuotes="maxQuotes"
            ></cmp-header-bar>
        </header>
        <section class="row">
            <cmp-input-box @quoteAdded="newQuote"></cmp-input-box>
        </section>
        <section class="row col-sm-12">
            <cmp-quote-grid
                :quotesProp="quotesData"
                @quoteDeleted="deleteQuote"
            ></cmp-quote-grid>
        </section>

        <footer class="row">
            <div class="col-sm-12">
                <div class="alert alert-info text-center">
                    Info: Clicca su una citazione per eliminarla.
                </div>
            </div>
        </footer>
    </div>
</template>

<script>
import HeaderBar from "./components/HeaderBar.vue";
import InputBox from "./components/InputBox.vue";
import QuoteGrid from "./components/QuoteGrid.vue";

export default {
    components: {
        "cmp-header-bar": HeaderBar,
        "cmp-input-box": InputBox,
        "cmp-quote-grid": QuoteGrid,
    },
    data: function () {
        return {
            quotesData: ["640 KB dovrebbero essere abbastanza per chiunque."],
            maxQuotes: 10,
            //textQuote: "",
        };
    },
    methods: {
        newQuote: function (quote) {
            if (this.quotesData.length >= 10) {
                alert("Limite massimo di citazioni raggiunto!");
            } else {
                this.quotesData.push(quote);
            }
        },

        deleteQuote(index) {
            this.quotesData.splice(index, 1);
        },
    },
};
</script>

<style></style>
