<template>
    <div v-show="false">
        <!-- Option API -->
        <input type="text" name="" id="" v-model="name">
        <!-- composition API -->
        <input type="text" name="" id="" v-model="firstName" placeholder="first Name">
        <input type="text" name="" id="" v-model="lastName" placeholder="last Name">

        <input type="text" name="" id="" v-model="fName" placeholder="F Name">
        <input type="text" name="" id="" v-model="lName" placeholder="L Name">
        <input type="text" name="" id="" v-model="options.heroName" placeholder="Hero Name">
    </div>
</template>

<script>
import {ref, watch, reactive, toRefs} from 'vue'
import _ from 'lodash'
    export default {
        name: 'replaceWatchers',
        setup() {

            const state = reactive({
                fName : '',
                lName: '',
                options: {
                    heroName : ''
                }
            })
            // watch(()=>{
            //     return {...state}
            // },function(newValue,oldValue){
            //     console.log('reactive old',oldValue.fName)
            //     console.log('reactive new',newValue.fName)
            //     console.log('reactive old',oldValue.lName)
            //     console.log('reactive new',newValue.lName)
            // })
            
            watch(()=> state.fName,function(newValue,oldValue){
                console.log('reactive old',oldValue)
                console.log('reactive new',newValue)
            })

            watch(()=> _.cloneDeep(state.options),function(newValue,oldValue){
                console.log('reactive old',oldValue)
                console.log('reactive new',newValue)
            },
            {
                deep: true,
            })

            const firstName = ref('')
            const lastName = ref('Arafat')

            watch([firstName,lastName],(newValue,oldValue) => {
                console.log('old',oldValue[0])
                console.log('new',newValue[0])
                console.log('old',oldValue[1])
                console.log('new',newValue[1])
            },{
                immediate: true
            })
            
            return{
                firstName,
                lastName,
                ...toRefs(state)
            }
        },
        data() {
            return {
                name: '',
            }
        },
        watch: {
            name(newValue, oldValue){
                console.log('old',oldValue)
                console.log('new',newValue)
            }
        }
    }
</script>

<style scoped>

</style>