<template>
    <div v-show="false">
        <input type="text" v-model="fName">
        <input type="text" v-model="lName">
        <PersonGreeting :firstName='fName' :lastName='lName' @callHeroes='callHeroes'></PersonGreeting>
    </div>
</template>

<script>
import {ref} from 'vue'
import PersonGreeting from './PersonGreeting.vue'
    export default {
        components:{
            PersonGreeting,
        },
        name:'Person',
        
        setup() {
            const fName = ref('')
            const lName = ref('')

            function callHeroes(hero){
                alert(`Calling ${hero}`)
            }
            return{
                fName,
                lName,
                callHeroes
            }
        }
    }
</script>

<style scoped>

</style>