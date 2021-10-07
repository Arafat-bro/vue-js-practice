<template>
    <div v-show="false">
        <input type="text" name="" id="" ref="inputRef">
        <input type="text" name="" id="" ref="inputRef2">
    </div>
</template>

<script>
import {ref,onMounted} from 'vue'
    export default {
        name:'templateRefComAPI',
        // mounted() {
        //     this.$refs.inputRef.focus()
        // },

        setup() {
            const inputRef2 = ref(null)
            onMounted(() => {
              inputRef2.value.focus()  
            })
            return{
                inputRef2
            }
        }
    }
</script>

<style scoped>

</style>