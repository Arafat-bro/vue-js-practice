<template >
    <div v-show="false">
        <h2>Data object name - {{o_name}}</h2>
        <h2>Data Composition API(setup - ref) name - {{c_name}}</h2>
        <h2>{{greet}}</h2>
    </div>
</template>

<script>
import { ref } from 'vue'

    export default { 
        name:'Data',
        setup(){
            const c_firstName = ref('Lee')
            const c_lastName = ref('kent')

            const greet = `Hello ${c_firstName.value} ${c_lastName.value}`
            return{
                c_firstName,
                c_lastName,
                greet
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