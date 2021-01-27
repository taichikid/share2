<template>
    <div class="header flex">
            <div class="header-logo">
                <img class="logo" src="../assets/logo.png">
            </div>
            <div class="header-right flex">
                <p @click="$router.push('/signup')">新規登録</p>
                <p @click="$router.push('/')">ログイン</p>
            </div>
        </div>
</template>

<style scoped>
.flex {
    display: flex;
    justify-content: space-between;
}
.logo {
    height: 40px;
    padding: 20px;
    cursor: pointer;
}
.header-right{
    padding: 30px;
}
.header-right p {
    margin-right: 20px;
    cursor: pointer;
}
.header {
    margin-bottom: 50px;
}
</style>