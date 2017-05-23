<template>
    <div>
        <div class="message">
            <h2>
                <slot></slot>
            </h2>
            <div v-for="item in messages">
                <h5>{{ item.messageTitle }}</h5>
                <p>{{ item.messageText }}</p>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['messages']
    }
</script>

<style lang="scss">
    .message {
        background-color: #efefec;
        border: 5px solid #bebebe;
        padding: 0.5em;
        p {
            color: #333333;
            text-align: left;
        }
        h5 {
            text-align: left;
            font-size: 1.5em;
            margin: 0;
        }
    }
</style>