<template>
    <form @submit.prevent="submit">
        <label for="">Email</label>
        <input type="email" name="email" v-model="email" required>
        <label for="">Password</label>
        <input type="password" name="email" v-model="password" required>
        <p class="error">{{ errorMsg }}</p>
        <label for="">Role : </label>
        <select v-model="role">
            <option value="Web Developer">Web Developer</option>
            <option value="Web Designer">Web Designer</option>
        </select>
        <div>
            <input type="checkbox" v-model="check">
            <label for="">Accept terms and condition</label>
        </div>
        <div>
            <label for="">Skill : </label>
            <input type="text" @keyup.alt="addSkill" v-model="skill">
        </div>
        <button>Submit</button>
    </form>
    <p>{{ email }} </p>
    <p> {{ password }}</p>
    <p> {{ role }}</p>
    <p> {{ check }}</p>
    <span v-for="skill in skills" :key="skill"><p> {{ skill }} <span class="cross" @click="deleteSkill(skill)">&#x2716;</span></p></span>
</template>

<script>
export default {
    data() {
        return {
            email: "",
            password: "",
            role: "",
            check: false,
            languages: [],
            skills : [],
            skill : '',
            errorMsg : '',
        }
    },
    methods: {
        addSkill(e) {
            if(e.key === ',' && this.skill){
                this.skills.push(this.skill);
                this.skill = "";
            }
        },
        deleteSkill(skill){
            this.skills = this.skills.filter(loopskill => {
                return loopskill != skill;
            })
        },
        submit(){
            if(this.password.length < 8){
                this.errorMsg = "Password Must be 8 character";
            }else{
                this.errorMsg = "";
            }
        }
    }
}
</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
    background: rgb(241, 239, 239);
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}

label {
    color: black;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}

input,
select {
    display: block;
    background: transparent;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid black;
    color: #555;
    outline: none;
}

input[type=checkbox] {
    display: inline-block;
    width: 16px;
    position: relative;
    top: 3px;
    margin-right: 10px;
}
.cross{
    cursor: pointer;
    margin-left: 15px;
    color: red;
    font-weight: bold;
}
button{
    display: block;
    padding: 5px 15px;
    margin:30px auto;
    background: rgb(58, 58, 190);
    color: white;
}
.error{
    color:red;
}
</style>