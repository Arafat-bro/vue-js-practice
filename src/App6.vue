<template>
<div>
    
        <Card></Card>
        <Card>Hello</Card>
        <Card><h2>Hi</h2></Card>
   
        <Card>
            <template v-slot:header>
                <div>Header</div>
            </template>
            <template v-slot:default>
                <div>
                    <img src="https://picsum.photos/200" alt="">
                </div>
            </template>
            <template v-slot:footer>
                <div>
                    <button>view details</button>
                </div>
            </template>
        </Card>
        <NameList>
            <template v-slot:default="slotProps">
                <div>
                    {{slotProps.fName}} {{slotProps.lName}}
                </div>
            </template>
        </NameList>
        <h3>App Component</h3>
        <childStyle><h3>Child Style Component by slot</h3></childStyle>
        
            <button @click="activeTab = 'TabA'">TabA</button>
            <button @click="activeTab = 'TabB'">TabB</button>
            <button @click="activeTab = 'TabC'">TabC</button>

        <!-- <TabA v-if="activeTab == 'TabA'"></TabA>
        <TabB v-if="activeTab === 'TabB'"></TabB>
        <TabC v-if="activeTab == 'TabC'"></TabC> -->
            <keep-alive> 
            <component :is="activeTab"></component>
            </keep-alive>
            
            <teleport to='#portal-root'>
            <Portal />
            </teleport>
        
    </div>
</template>

<script>
    import Card from './components/Card.vue'
    import NameList from '@/components/NameList'
    import childStyle from '@/components/childStyle'
    import TabA from '@/components/TabA'
    import TabB from '@/components/TabB'
    import TabC from '@/components/TabC'
    import Portal from '@/components/Portal.vue'
    export default {
        name:'App6',
        components:{
            Card,
            NameList,
            childStyle,
            TabA,
            TabB,
            TabC,
            Portal,
        },
        data() {
            return {
                activeTab : 'TabB'
            }
        },
    }
</script>

<style scoped>
h3{
    color: olivedrab;
}
</style>