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
    </form>
    <p>{{ email }} {{ password }} {{ role }}</p>
</template>

<script>
export default {
data(){
    return{
        email : "",
        password : "",
        role : ""
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
</style>