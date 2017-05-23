<template>
    <div>
        <h2>{{ quoteText }}</h2>
        <p>{{ quotePerson }}</p>
        <button @click="getQuote()">New quote</button>
    </div>
</template>

<script>
import axios from 'axios'

export default {
    mounted () {
        this.getQuote()
    },
    data () {
        return {
            quotePerson: "",
            quoteText: ""
        }
    },
    methods: {
        getQuote: function () {
            axios.get("http://quotesondesign.com/wp-json/posts?filter[orderby]=rand").then((response) => {
                this.quotePerson = response.data[0].title;
                this.quoteText = response.data[0].content.replace("<p>", "").replace("</p>", "");
            })
        }
    }
}
</script>

<style lang="scss">
    h2 {
        max-width: 60%;
        margin: 0px auto;
        padding-top: 2em;
    }
    button {
        font-size: 2em;
        padding: 2em;
        background-color: transparent;
        border: none;
        &:active {
            border: none;
        }
    }
    
</style>