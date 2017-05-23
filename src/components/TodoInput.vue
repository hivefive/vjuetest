<template>
    <div>
        <input type="text"
        v-model="messageTitle"
        placeholder="Add message title"
        >
        <input type="text"
        v-model="messageText"
        placeholder="Add message"
        v-on:keyup.enter="addMessage()"
        >
        <input type="text"
        v-model="todo"
        placeholder="Add todo"
        v-on:keyup.enter="addTodo()"
        >
    </div>
</template>

<script>
    export default {
        props: ["messages", "myList"],
        methods: {
            addMessage: function () {
                var messageObj = {
                    messageTitle: this.messageTitle,
                    messageText: this.messageText
                }
                this.messages.push(messageObj)
                this.messageTitle = ""
                this.messageText = ""
            },
            addTodo: function () {
                this.myList.push(this.todo)
                this.todo = ""
            }
        },
        data: function () {
            return {
                messageTitle: "",
                messageText: "",
                todo: ""
            }
        }
    }
</script>

<style lang="scss">
    input {
        padding: 0.5em;
    }
</style>