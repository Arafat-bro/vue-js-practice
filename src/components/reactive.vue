<template>
    <div v-show="false">
        <h2>{{greet}}</h2>
        <h2>{{reactiveGreet}}</h2>
    </div>
</template>

<script>
import { ref, reactive } from 'vue'

    export default { 
        name:'Data',
        setup(){
            const c_firstName = ref('Lee')
            const c_lastName = ref('kent')

            const greet = `Hello ${c_firstName.value} ${c_lastName.value}`

            const profile = reactive({
                fName : 'Princess',
                lName : 'Diana',
                heroName : 'Wonder Woman',
            })
            const reactiveGreet = `Hello ${profile.fName} ${profile.lName} a.k.a ${profile.heroName}`
            return{
                c_firstName,
                c_lastName,
                greet,
                profile,
                reactiveGreet,
            }
        },
        data() {
            return {
                o_name : 'Bruce'
            }
        },
    }
</script>

<style scoped>

</style>