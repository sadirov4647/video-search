<template>
    <div v-if="response">
        {{ response.snippet.title }}
    </div>
</template>

<script>
    export default {
        name:'VideoDetail',
        props:['response']
    }
</script>

<style scoped>

</style>