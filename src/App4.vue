<template>
  <div>
    {{ firstName }} {{ lastName }} <br />
    {{ fullName }} <br />
    <p>
      <button
        v-once
        @click="items.push({ id: 4, title: 'computer', price: 50 })"
      >
        Add</button
      ><br />
      {{ total }}
    </p>
    <p>Volume Range (0-20)</p>
    <p>{{ volume }}</p>
    <button @click="volume += 2" v-if="volume < 20">Increase</button>
    <button @click="volume -= 2" v-if="volume > 0">Decrease</button><br/>
    <input type="text" v-model.lazy="movie" />
    <input type="text" v-model="movieInfo.actor" />
    <input type="text" v-model="movieInfo.title" />
    <div><button @click="movieList.push('wonder woman')">Add Movie</button></div>
  <!--with reference -->
  <button @click="movieList2 = movieList2.concat(['wonder woman 2'])">Add Movie 2</button> </div>
</template>

<script>
export default {
  name: "App4",
  data() {
    return {
      firstName: "Bruce",
      lastName: "Lee",
      items: [
        {
          id: 1,
          title: "phone",
          price: 100,
        },
        {
          id: 2,
          title: "laptop",
          price: 200,
        },
        {
          id: 3,
          title: "mobile",
          price: 150,
        },
      ],
      volume: 0,
      movie: "Batman",
      movieInfo : {
        title: '',
        actor : '',
      },
      movieList : ['Batman','superman '],
      movieList2 : ['New movie', 'with direct reference']
    };
  },
  methods: {},
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
    total() {
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        null
      );
    },
  },
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert("It's already higher volume");
      }
    },
    // movie+(newValue){
    //     console.log(`Calling API with movie ${newValue}`);
    // }
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie ${newValue}`);
      },
      immediate: true,
    },
    movieInfo: {
        handler(newValue){
            console.log(`Calling API with title = ${newValue.title} and actor = ${newValue.actor}`);
        },
        deep:true
    },
    movieList:{
        handler(newValue){
            console.log(`Updated list ${newValue}`);
        },
        deep: true
    },
    movieList2: {
        handler(newValue){
            console.log(`New Updated List2 ${newValue}`);
        }
    }
  },
};
</script>

<style>
#app4{
text-align: center;
}
</style>
