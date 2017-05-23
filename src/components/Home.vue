<template>
    <div class="home-screen">
        <p>Lorem ipsum home page with test to show that you thought I wrote text because that is what was supposed to be written.</p>
        <p>There is something to be said for all the jibberish written to show text in sample form.</p>
        <ul>
            <li v-for="item in myList">
                {{ item }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        props: ['myList']
    }
</script>

<style lang="scss">
    .home-screen {
        p {
            font-family: monospace;
        }
        li {
            display: block;
            text-align: left;
            margin: 0px auto;
            margin-left: 31%;
        }
    }
</style>