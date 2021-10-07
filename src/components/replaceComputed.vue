<template>
    <div v-show="false">
        <input type="text" v-model="fname">
        <input type="text" v-model="lname">
        <h2>Options Full name - {{fullname}}</h2>

        <input type="text" v-model="refFirstname">
        <input type="text" v-model="refLastname">
        <h2>Composition Full name - {{refFullname}}</h2>

        <input type="text" v-model="reactiveFname">
        <input type="text" v-model="reactiveLname">
        <h2>Composition Full name - {{reactiveFullname}}</h2>

    </div>
</template>

<script>
import {ref, computed, reactive, toRefs} from 'vue'
    export default {
        name:'replaceComputed',
        setup() {
            const refFistname = ref('')
            const refLastname = ref('')
            
            const refFullname = computed(() =>{
                return `${refFistname.value} ${refLastname.value}`
            })

            const state = reactive({
                reactiveFname : '',
                reactiveLname : ''
            })

            const reactiveFullname = computed(()=>{
                return `${state.reactiveFname} ${state.reactiveLname}`
            })

            return{
                refFistname,
                refLastname,
                refFullname,
                ...toRefs(state),
                reactiveFullname
            }
        },
        data() {
            return {
                fname: '',
                lname: ''
            }
        },
        computed:{
            fullname(){
                return `${this.fname} ${this.lname}`
            }
        }
    }
</script>

<style scoped>

</style>