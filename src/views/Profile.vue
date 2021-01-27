<template>
  <div class="flex">
    <div class="left">
      <SideNavi />
    </div>
    <div class="right">
      <div class="title">
        <p>プロフィール</p>
      </div>
      <div class="profile">
          <div class="flex-profile">
              <p class="profile-name">{{name}}</p>
              <div @click="edit">
                  <button>変更する</button>
              </div>
          </div>
          <p class="text" v-if="active">{{profile}}</p>
          <input type="text" v-model="profile" v-else />
      </div>
      <Message />
    </div>
  </div>
</template>

<script>
import SideNavi from "../components/SideNavi";
import Message from "../components/Message";
export default {
  data() {
    return {
      active: true,
      name: "太郎",
      profile: "私は太郎です"
    };
  },
  components: {
    SideNavi,
    Message
  }
};
</script>

<style scoped>
.flex {
  display: flex;
}
.left {
  width: 22%;
}
.right {
  width: 78%;
}
.logo {
  width: 100px;
  margin-bottom: 20px;
}
img {
  width: 25px;
  height: 25px;
}
.title {
  border-bottom: 1px solid white;
  border-left: 1px solid white;
  padding: 15px;
}
.title p {
  font-size: 20px;
  font-weight: bold;
}
.profile {
  padding: 20px;
  border-bottom: solid 1px white;
  border-left: 1px solid white;
}
.profile-name {
  font-size: 24px;
}
.flex-profile {
    display: flex;
    justify-content: space-between;
}
button {
  display: block;
  margin: 10px 0 0 auto;
  background-color: #5419da;
  border-radius: 25px;width: 100px;
  text-align: center;
  padding: 8px 0 10px;
}
</style>