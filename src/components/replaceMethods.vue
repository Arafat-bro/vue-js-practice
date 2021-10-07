<template>
    <div v-show="false">
        <h3>Normal Method - {{name}}</h3>
        <button @click="setName">Change Name</button>

        <h2>composition api - {{count}}</h2>
        <button @click="increament">increament</button>
        <h2>Reactive & toRefs - {{first}} {{last}}</h2>
        <button @click="changeHero">Change Hero</button>
    </div>
</template>

<script>
import {ref, reactive, toRefs} from 'vue'
    export default {
        name: 'replaceMethods',
        setup() {
            const count = ref(0)
            function increament(){
                count.value++
            }

            const state = reactive({
                first : 'Bruce',
                last : 'Lee'
            })
            function changeHero(){
                state.first = 'Sirajuddaula',
                state.last = 'Arafat'
            }
            
            return{
                count,
                increament,
                ...toRefs(state),
                changeHero
            }
        },
        data() {
            return {
                name : 'Arafat',
            }
        },
        methods: {
            setName(){
                this.name = 'Sirajuddaula'    
            }
        },
    }
</script>

<style scoped>

</style>