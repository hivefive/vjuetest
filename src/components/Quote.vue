<template>
    <div>
        <h2 v-html="quoteText"></h2>
        <p>- {{ quotePerson }}, {{ quoteYear }}</p>
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
            quoteText: "",
            quoteYear: Math.floor(Math.random() * 1000)
        }
    },
    methods: {
        getQuote: function () {
            axios.get("http://quotesondesign.com/wp-json/posts?filter[orderby]=rand").then((response) => {
                this.quotePerson = response.data[0].title
                this.quoteYear = 1000 + Math.floor(Math.random() * 1000)
            }).catch((response) => {
                console.log("Error:" + response)
            })
            axios.get("http://quotesondesign.com/wp-json/posts?filter[orderby]=rand").then((response) => {
                this.quoteText = response.data[0].content
            }).catch((response) => {
                console.log("Error:" + response)
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
        min-height: 3.5em;
    }
    button {
        font-size: 2em;
        padding: 1em;
        margin-bottom: 1em;
        background-color: transparent;
        border: none;
        &:active {
            border: none;
        }
    }
    
</style>