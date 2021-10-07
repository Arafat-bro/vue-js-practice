<template>
    <div>
        <h3>Child Component B -</h3>
        <child-c></child-c>
    </div>
</template>

<script>
 import ChildC from './ChildC.vue'
    export default {
        components:{
            ChildC,
        },
        name:'ChildB',
       
    }
</script>

<style scoped>

</style>