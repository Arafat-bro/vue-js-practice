<template>
    <div v-show="false">
   <!-- <div>
        <slot>Default Content</slot>
    </div>  -->
    <div>
        <slot name="header"></slot>
    </div>
    <div>
        <slot></slot>
    </div>
    <div>
        <slot name="footer"></slot>
    </div>
    </div>
</template>

<script>
    export default {
       name:'Card', 
    }
</script>

<style scoped>

</style>