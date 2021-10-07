<template>
<div>
<h2> {{ name }} </h2>
<h2 v-html="major"></h2>
<h2 v-bind:id="headingId">Heading</h2>
<button v-bind:disabled="isDisabled">button</button>
<h2 v-bind:class="status">Status</h2>
<h2 v-bind:class="isPromoted && 'promoted'">PROMOTED</h2>
<h2 v-bind:class="isSoldout ? 'sold-out' : 'new'">Soldout?</h2>
<h2 :class="['new','promoted']">New Promoted</h2>
<h2 :class="[isPromoted && 'promoted',isSoldout ? 'sold-out' : 'new']">Array conditional classes</h2>
<h2 :class="{
  promoted: isPromoted,
  'sold-out': isSoldout,
  new: !isSoldout
}">Object conditional</h2>
<h2 :style="{
  color:hightlightColor,
  'font-size' : headerSize + 'px',
  border : '2px solid black'
}">Styled Text</h2>
<p :style="EasyStyleObject">Easy Styled Object</p>
</div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      name : "Arafat",
      major: "<b>agriculture</b>",
      headingId: "heading",
      isDisabled : "true",
      status: "danger",
      isPromoted : true,
      isSoldout: true,
      hightlightColor : 'orange',
      headerSize : 50,
      EasyStyleObject : {
        color : 'royalblue',
        'font-size' : '40px',
        border : '1px solid black'
      },
    };
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.danger{
  color: darkred;
}
.underline{
  text-decoration: underline;
}
.promoted{
  font-style: italic
}
.sold-out{
  color: red;
}
.new{
  color:green;
}
</style>
