<template>
    <div>
<h3>Child Component C - {{username}}</h3>
<h3>Child Component Composition Childcount C - {{childCount}}</h3>
<h3>Child Component Composition childHero C - {{fName}} {{lName}}</h3>
<button @click="increamentCount"> Increament Count Button from Child</button>
    </div>
</template>

<script>
import {inject,toRefs} from 'vue'

    export default {
        name:'ChildC',
        inject:['username'],

        setup() {
            const userName = inject('c_username','default- if not passed')
            const childCount = inject('c_count',0)
            const increamentCount = inject('increamentCount')
            const childHero = inject('c_hero',{})
            return{
                userName,
                childCount,
                ...toRefs(childHero),
                increamentCount
            }
        }
    }
</script>

<style scoped>

</style>
