<template>
    <div>
        <h3>Child Component A -</h3>
        <child-b></child-b>
    </div>
</template>

<script>
import ChildB from './ChildB.vue'
    export default {
        components:{
            ChildB,
        },
        name:'ChildA',
       
    }
</script>

<style scoped>

</style>