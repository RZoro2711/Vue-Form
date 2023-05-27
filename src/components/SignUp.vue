<template>
    <form action="">
        <label for="">Email</label>
        <input type="email" name="email" v-model="email" required>
        <label for="">Password</label>
        <input type="password" name="email" v-model="password" required>
        <label for="">Role : </label>
        <select v-model="role">
            <option value="Web Developer">Web Developer</option>
            <option value="Web Designer">Web Designer</option>
        </select>
        <div>
            <input type="checkbox" v-model="check">
            <label for="">Accept terms and condition</label>
        </div>
        <!-- Multi ckechbox -->
        <label for="">Check language</label>
        <div>
            <input type="checkbox" value="JavaScript" v-model="languages">
            <label for="">JavaScript</label>
        </div>
        <div>
            <input type="checkbox" value="PHP" v-model="languages">
            <label for="">PHP</label>
        </div>
        <div>
            <input type="checkbox" value="Python" v-model="languages">
            <label for="">Python</label>
        </div>
        <div>
            <input type="checkbox" value="Ruby" v-model="languages">
            <label for="">Ruby</label>
        </div>
        <div>
            <input type="checkbox" value="Java" v-model="languages">
            <label for="">Java</label>
        </div>
    </form>
    <p>{{ email }} {{ password }} {{ role }} {{ check }} {{ languages }}</p>
</template>

<script>
export default {
data(){
    return{
        email : "",
        password : "",
        role : "",
        check : false,
        languages : [],
    }
}
}
</script>

<style>
form{
    max-width: 420px;
    margin: 30px auto;
    background: rgb(241, 239, 239);
    text-align: left;
    padding: 40px;
    border-radius: 10px;
}
label{
    color: black;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
}
input, select{
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
input[type=checkbox]{
    display: inline-block;
    width: 16px;
    position: relative;
    top: 3px;
    margin-right: 10px;
}
</style>