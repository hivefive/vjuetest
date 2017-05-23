<template>

    <nav class="nav">
        <ul class="nav-left">
            <slot></slot>
        </ul>
    </nav>

</template>

<script>
    export default {
        data: function () {
            return {
                currentScreen: "home"
            }
        }
    }
</script>

<style lang="scss">
    nav {
        width: 100%;
        ul {
            width: 60%;
            margin: 0px auto;
            a {
                cursor: pointer;
                width: 24%;
                display: inline-block;
                padding-bottom: 0.3em;
                border-bottom: 2px solid transparent;
            }
        }
        .is-active {
            border-bottom: 2px solid #54e5a2;
            transition: 0.6s;
            color: #4ed898;
        }
    }
</style>