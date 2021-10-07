<template>
    <div>
        <template-ref></template-ref>
        <click-counter></click-counter>
        <hover-counter></hover-counter>
        <Data></Data>
        <reactive></reactive>
        <Demo1></Demo1>
        <demo2></demo2>
    </div>
</template>

<script>
import TemplateRef from '@/components/TemplateRef'
import ClickCounter from '@/components/ClickCounter'
import HoverCounter from '@/components/HoverCounter'
import Data from './components/Data.vue'
import reactive from '@/components/reactive'
import Demo1 from '@/components/Demo1'
import Demo2 from '@/components/Demo2'
    export default {
        name:'App8',
        components:{
            TemplateRef,
            ClickCounter,
            HoverCounter,
            Data,
            reactive,
            Demo1,
            Demo2,
        }
    }
</script>

<style scoped>

</style>