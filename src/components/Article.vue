<template>
    <div v-show="false">
       <h2 v-bind="$attrs"> {{title}} {{likes}} {{ispublished ? 'yes' : 'no'}}</h2>
    </div>
</template>

<script>
    export default {
        name : 'Article',
        props: {
            title: {
                type: String,
                required: true,
                default: 'This is default value'
            },
            likes: Number,
            ispublished : Boolean,
        },
        inheritAttrs : false,
    }
</script>

<style scoped>

</style>