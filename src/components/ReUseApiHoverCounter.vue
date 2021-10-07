<template>
    <div>
        <button @mouseover="increament">Hovered {{count}}</button>
    </div>
</template>

<script>
// import CounterMixin from '../Mixins/Counter'
import useCounter from '@/composables/useCounter'
    export default {
        name:'ReUseApiHoverCounter',
        // mixins:[CounterMixin]
        setup() {
            const {count,increament} = useCounter(20,30)

            return{
                count,
                increament
            }
        }
    }
</script>

<style scoped>

</style>