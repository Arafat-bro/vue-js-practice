<template>
<div>
    <div>
        <pre>
        {{JSON.stringify(formValues,null,2)}}
        </pre>
    </div>
    <div>
        <form @submit.prevent="submitForm">
            <label for="name ">Name </label>
            <input type="text" id="name" v-model.trim.lazy="formValues.name"><br><br>
            <label for="profile">Profile Summary</label>
            <textarea cols="30" rows="1" v-model.lazy="formValues.profileSummary"></textarea>
            <br><br>
            <label>Select Country </label>
            <select name="" id="" v-model="formValues.country">
                <option value="Bangladesh">Bangladesh</option>
                <option value="Qatar">Qatar</option>
                <option value="Germany">Germany</option>
            </select>
             <br><br>
             <label>Job Location </label>
            <select name="" id="" multiple v-model="formValues.jobLocation">
                <option value="Bangladesh">Bangladesh</option>
                <option value="Qatar">Qatar</option>
                <option value="Germany">Germany</option>
            </select><br><br>
            <input type="checkbox" id="remoteWork" v-model="formValues.remoteWork" true-value="yes" false-value="no">
            <label for="remoteWork">Open for remote work?</label><br/><br/>
            <div>
                <label for="skillset"> Set Skills :-</label><br/>
                <input type="checkbox" id="html" value="html" v-model="formValues.skillset">
                <label for="html">HTML</label><br/>
                <input type="checkbox" id="cs" value="css" v-model="formValues.skillset">
                <label for="css">CSS</label><br/>
                <input type="checkbox" id="js" value="javascript" v-model="formValues.skillset">
                <label for="javascript">javascript</label><br/>
            </div><br/>
            <div>
                <label for="exp">Year of Experience</label><br/>
                <input type="radio" id="0-2" value="0-2" v-model="formValues.yearOfExperience">
                <label for="0-2">0-2</label><br/>
                <input type="radio" id="3-5" value="3-5" v-model="formValues.yearOfExperience">
                <label for="3-5">3-5</label><br/>
                <input type="radio" id="6-10" value="6-10" v-model="formValues.yearOfExperience">
                <label for="6-10">6-10</label><br/>
                <input type="radio" id="10+" value="10+" v-model="formValues.yearOfExperience">
                <label for="10+">More than 10</label><br/>
            </div>
            <div>
                <label for="age">Age</label>
                <input type="number" @keyup.enter="submitForm" v-model.number="formValues.age"> 
            </div>
            <!-- <div>
            <button>Submit</button>
            </div> -->
        </form>
    </div>
</div>
</template>

<script>
export default {
    name: 'App3',
    data() {
        return {
            formValues: {
                name: '',
                profileSummary: '',
                country: '',
                jobLocation : [],
                remoteWork : "no",
                skillset:[],
                yearOfExperience:'',
                age: null,
            }
        }
    },
    methods: {
        submitForm(){
            console.log('Form Values', this.formValues);
        }
    }
}
</script>

<style>
#app3{
text-align: center;
}
</style>
