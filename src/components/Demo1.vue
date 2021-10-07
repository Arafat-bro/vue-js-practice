<template>
    <div v-show="false">
        <h2>{{name}}</h2>
    </div>
</template>

<script>
import { ref } from 'vue'
import { setTimeout } from 'timers';
    export default {
        name: 'Demo1',
        setup() {
            const name = ref('Arafat')

            setTimeout(()=>{
                name.value = 'Sirajuddaula'
            },2000)
            return{
                name,
            }
        }
    }
</script>

<style scoped>

</style>