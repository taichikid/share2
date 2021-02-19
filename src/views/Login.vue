<template>
    <div>
        <HeaderAuth />
        <div class="card">
            <p>ログイン</p>
            <div class="form">
                <input placeholder="メールアドレス" type="email" v-model="email">
                <input placeholder="パスワード" type="password" v-model="password">
                <button @click="auth">ログイン</button>
            </div>
        </div>
    </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth";
export default {
    data() {
        return {
            email:"",
            password: ""
        };
    },
    components: {
        HeaderAuth
    },
    methods: {
        aurh() {
            this.$store.dispatch("login", {
                email: this.email,
                password: this.password
            });
        }
    }
};
</script>

<style scoped>
.flex {
    display: flex;
    justify-content: space-between;
}
.card {
    margin: 100px auto;
    text-align: center;
    background-color: white;
    width: 350px;
    padding: 20px;
    border-radius: 10px;
}
.card p {
    color: black;
    font-weight: bold;
}
.form {
    display: inline-box;
}
input {
    margin-top: 20px;
    border: solid 1px black;
    width: 80%;
    height: 30px;
    border-radius: 10px;
}
button {
    background-color: #4a27d1;
    margin-top: 20px;
    border-radius: 25px;
    padding: 10px 20px;
    cursor: pointer;
}
</style>

