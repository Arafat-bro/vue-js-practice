<template>
    <div>
        <Greet name="Arafat" alias="Superman"/>
        <Greet name="Boss" alias="Batman"/>
        <Greet name="Brother" alias="Pieman"/>
        <Greet :name="name" :alias="from"/>
        <Article id="my-airticle" title="Aricle title" :likes="50" :ispublished="true" />
        <button @click="showPopup = true">Show Popup</button>
        <popup v-show="showPopup" @close="closePopup"></popup>
    </div>
</template>


<script>
import Greet from './components/Greet.vue'
import Article from './components/Article.vue'
import Popup from '@/components/Popup'
    export default {
        name: 'App5',
        components:{
            Greet,
            Article,
            Popup
        },
        data(){
            return{
                name : "from",
                from : "data",
                showPopup : false,
                
            }
        },
        methods:{
            closePopup(name){
                this.showPopup=false
                console.log('name',name)
            }
        }
    }
</script>

<style scoped>
#app5{
    text-align: center;
}
</style>