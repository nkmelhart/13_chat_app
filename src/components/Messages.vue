<template>
  <Message v-for="(m, index) in messages" :key="index" :message="m"/>
  <NewMessage />
</template>

<script>

    import { database } from '../helpers/useFirebase'

    export default{

        setup(){
        const { messages } = database()
        console.log(messages)

        return {messages}
        }
    }
</script>