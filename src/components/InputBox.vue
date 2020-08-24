<template>
    <div>
        <form action="">
            <div
                class="col-sm-8 col-sm-2-offset col-xs-12 col-md-6 col-md-offset-3 form-group"
            >
                <label>Citazione</label>
                <textarea
                    v-model="quote"
                    class="form-control"
                    name=""
                    cols="30"
                    rows="5"
                ></textarea>
            </div>
            <div
                class="col-sm-8 col-sm-2-offset col-xs-12 col-md-6 col-md-offset-3 form-group"
            >
                <button class="btn btn-primary" @click.prevent="createNew">
                    Salva citazione
                </button>
            </div>
        </form>
    </div>
</template>

<script>
export default {
    data: function () {
        return {
            quote: "",
        };
    },
    methods: {
        createNew: function () {
            if (this.quote) {
                this.$emit("quoteAdded", this.quote);
                this.quote = "";
            }
        },
    },
};
</script>

<style scoped></style>
