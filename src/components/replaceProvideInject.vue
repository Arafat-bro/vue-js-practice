<template>
    <div v-show="false">
        <h3>Parent Component - {{name }}</h3>
        <h3>Parent Component Composition count - {{count }}</h3>
        <h3>Parent Component Composition hero - {{fName }} {{lName}}</h3>
        <button @click="increament">Increament Count</button>
        <child-a></child-a>
    </div>
</template>

<script>
import ChildA from './ChildA.vue'
import {provide, ref, reactive, toRefs} from 'vue'
    export default {
        components:{
            ChildA,
        },
        name: 'replaceProvideInject',
         data() {
            return {
                name : 'Arafat',
            }
        },
        provide(){
            return{
                username: this.name,
            }
        },
        setup() {
            provide('c_username','Siraj')

            const count = ref(0)
            function increament(){
                count.value++
            }

            const state = reactive({
                fName: 'Bruce',
                lName:'Wayne'
            })
            provide('c_count',count)
            provide('c_hero',state)
            provide('increamentCount',increament)

            return{
                count,
                ...toRefs(state),
                increament
            }
        }
    }
</script>

<style scoped>

</style>