<template>
    <div>
        
        <!-- <h2>{{profile.fName}} {{profile.lName}}</h2> -->
        <!-- <h3>{{firstName}} {{lastName}}</h3> -->
        <h3>{{fName}} {{lName}}</h3>
    </div>
</template>

<script>
import { reactive, toRefs } from 'vue'
import { setTimeout } from 'timers';

    export default {
        name: 'Demo2',
        setup() {
            const profile = reactive({
                fName : 'Siraj',
                lName : 'Arafat'
            })

            setTimeout(()=>{
                profile.fName = 'Bruce',
                profile.lName = 'Wayne'
                
            },2000)

            //return toRefs(profile)
            // return{
            //     profile,
            // }
            return toRefs(profile)
        }
    }
</script>

<style scoped>

</style>