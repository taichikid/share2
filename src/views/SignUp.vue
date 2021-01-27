<template>
    <div>
        <HeaderAuth />
        <div class="card">
            <p>新規登録</p>
            <div class="form">
                <input placeholder="ユーザーネーム" type="name">
                <input placeholder="プロフィール" type="profile">
                <input placeholder="メールアドレス" type="mail">
                <input placeholder="パスワード" type="password">
                <button>新規登録</button>
            </div>
        </div>
    </div>
</template>

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