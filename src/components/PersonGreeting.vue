<template>
    <div v-show="false">
        <h2> Hello! {{fullName}}</h2>
        <h2>Hi! {{fullname}}</h2>
        <button @click="sendEvent">Call Hero</button>
    </div>
</template>

<script>
import {computed} from 'vue'
    export default {
        name:'PersonGreeting',
        props:['firstName','lastName'],
        emits:['callHeroes'],
        computed:{
            fullName(){
                return `${this.firstName} ${this.lastName}`
            }
        },
        setup(props, context) {
            console.log(context)
            const fullname = computed(()=>{
                return `${props.firstName} ${props.lastName}`
            })

            function sendEvent(){
                context.emit('CallHeroes',fullname.value)
            }
            return{
                fullname,
                sendEvent
            }
        }
    }
</script>

<style scoped>

</style>