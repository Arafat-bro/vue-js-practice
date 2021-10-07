<template>
    <div>
<h2 v-show="show">Used v-show</h2>
 <div v-if="display">
     <h2 v-if="num === 0">This is a Zero</h2>
     <h2 v-else-if="num > 0"> The number is positive</h2>
     <h2 v-else-if="num < 0"> The number is Negative</h2>
     <h2 v-else> This is not a number</h2>
 </div>
 <h2 v-for="(name,index) in names" :key="name">{{ index + 1 }} - {{ name }}</h2>
 <h2 v-for="name in fullNames" :key="name.first">{{name.first}} {{name.last}}</h2>
 <div v-for="actor in actors" :key="actor.name"><p> {{actor.name}}</p>
 <span v-for="movie in actor.movies" :key="movie"> {{'- ' + movie}}</span> </div>
<h2>The Multiplication is {{ multiply(baseValue) }}</h2>
<p>{{name}}</p>
<button v-on:click="name = 'Superman'">Click</button>
<p>{{count}}</p>
<div>
    <button @click="increament()">Increament</button>
    <button @click="decreament()">Decreament</button>
</div>
    </div>
</template>

<script>
export default {
    name: 'App2',
    data() {
        return {
            num : 5.3,
            display: true,
            show : true,
            names: ['Arafat','Sarafat','Jerin'],
            fullNames : [
                {first : 'Bruce', last : 'lee'},
                {first: 'Mahmuda', last: 'Akter'},
                {first: 'Jhon', last: 'Doe'},
            ],
            actors : [
                {
                    name : 'Chritian Bale',
                    movies : ['Batman', 'The Prestige']
                },
                {
                    name: 'Di Caprio',
                    movies : ['Titanic', 'ubhInception']
                }
            ],
            baseMultiplyer: 5,
            baseValue : 2,
            name : 'batman',
            count: 0
        }
    },
    methods: {
        add(a,b,c){
            return a + b +c
        },
        multiply(num){
            return num * this.baseMultiplyer
        },
        increament(){
            this.count += 1
        },
        decreament(){
            this.count -= 1
        }
    },    
}
</script>

<style>
#App2{
   font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}
</style>

