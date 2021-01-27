<template>
  <div>
    <div class="left-padding">
        <img class="logo" src="../assets/logo.png" alt="">
        <div class="flex icon-field">
          <img src="../assets/home.png" alt="">
          <p>ホーム</p>
        </div>
        <div class="flex icon-field">
          <img src="../assets/profile.png" alt="">
          <p>プロフィール</p>
        </div>
        <div class="flex icon-field">
          <img src="../assets/logout.png" alt="">
          <p>ログアウト</p>
        </div>
    </div>
    <ShareMessage />
  </div>
</template>

<script>
import ShareMessage from "../components/ShareMessage";
export default {
    components: {
        ShareMessage
    }
}
</script>

<style scoped>
.flex {
  display: flex;
}
.left-padding {
  margin: 20px;
}
.logo {
  width: 100px;
  margin-bottom: 20px;
}
.icon-field {
  margin-bottom: 20px;
  cursor: pointer;
}
.icon-field p {
  font-size: 16px;
  padding-left: 15px;
}
img {
  width: 25px;
  height: 25px;
}
</style>