<template>
    <div>
        <button @click="increament">Clicked {{count}}</button>
    </div>
</template>

<script>
// import CounterMixin from '../Mixins/Counter'
import useCounter from '@/composables/useCounter'
    export default {
        name:'ReUseApiClickCounter',
        // mixins: [CounterMixin],
        setup() {
            const {count,increament} = useCounter(100,10)

            return{
                count,
                increament
            }
        }
    }
</script>

<style scoped>

</style>