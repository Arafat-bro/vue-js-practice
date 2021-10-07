<template>
    <div v-show="false">
        <input type="text" ref="inputRef">
    </div>
</template>

<script>

    export default {
        name:'TemplateRef',
        mounted() {
            this.$refs.inputRef.focus()
        },
    }
</script>

<style scoped>

</style>