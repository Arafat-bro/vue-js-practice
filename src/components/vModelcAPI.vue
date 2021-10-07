<template>
    <div v-show="false">
        <form @change="submitForm">
        <input type="text" placeholder="first Name" id="" v-model="fName" >
        <input type="text" placeholder="last Name" id="" v-model="lName" >
        <input type="text" v-model="firstName">
        <input type="text" v-model="lastName">
        <input type="text" v-model="heroName">
        </form>
    </div>
</template>

<script>
import {ref, reactive, toRefs} from 'vue'

    export default {
        name: 'vModelcAPI',
        setup() {
            const heroName = ref('')
            const state = reactive({
                firstName : '',
                lastName : ''
            })
            return{
                heroName,
                ...toRefs(state)
                
            }
        },
        data(){
            return{
                fName : '',
                lName : '',
            }
        },
        methods: {
            submitForm(){
                console.log(this.fName, this.lName,this.heroName)
            }
        },
        
    }
</script>

<style scoped>

</style>