<template>
    <div v-show="true">
        <slot></slot>
        <div>
        <h3>Child Style from its component</h3>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'childStyle',
        data() {
            return {
                
            }
        },
    }
</script>

<style scoped>
h3{
    color:orange;
}
</style>