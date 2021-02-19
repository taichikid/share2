<template>
    <div>
        <HeaderAuth />
        <div class="card">
            <p>新規登録</p>
            <div class="form">
                <input placeholder="ユーザーネーム" type="name" v-model="name">
                <input placeholder="プロフィール" type="profile" v-model="profile">
                <input placeholder="メールアドレス" type="mail" v-model="email">
                <input placeholder="パスワード" type="password" v-model="password">
                <button @click="auth">新規登録</button>
            </div>
        </div>
    </div>
</template>

<script>
import HeaderAuth from "../components/HeaderAuth";
import axios from "axios";
export default {
    data() {
        return {
            name: "",
            profile: "",
            email: "",
            password: ""
        };
    },
    components: {
        HeaderAuth
    },
    methods: {
        auth() {
            axios
              .post("https://radiant-sea-99974.herokuapp.com/api/register", {
                  name: this.name,
                  profile: this.profile,
                  email: this.email,
                  password: this.password
              })
              .then(response => {
                  console.log(response);
                  this.$router.replace("/");
              })
              .catch(error => {
                  alert(error);
              });
        }
    }
};
</script>

<style scoped>
.card {
    margin: 0 auto;
    width: 350px;
    text-align: center;
    padding: 20px;
    border-radius: 10px;
    background-color: white;
}
.card p {
    font-weight: bold;
    color: black;
}
input {
    margin-top: 20px;
    width: 80%;
    height: 30px;
    border: solid 1px black;
    border-radius: 10px;
}
button {
    background-color: #4a27d1;
    margin-top: 20px;
    border-radius: 25px;
    padding: 10px 30px;
    cursor: pointer;
}
</style>

<script>
import HeaderAuth from "../components/HeaderAuth"
export default {
   components: {
       HeaderAuth
   } 
}
</script>