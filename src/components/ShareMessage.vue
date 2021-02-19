<template>
    <div class="share">
        <p>シェア</p>
        <textarea v-model="share"></textarea>
        <div @click="send">
          <button>シェアする</button>
        </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      share: "",
    };
  },
  methods: {
    send() {
      if (this.share === "") {
        alert("シェアする内容を入力してください");
      } else {
        axios
          .post("https://radiant-sea-99974.herokuapp.com/api/shares", {
            user_id: this.$store.state.user.id,
            share: this.share,
          })
          .then((response) => {
            console.log(response);
            alert("シェアしました");
            this.share = "";
            this.$router.go({
              path: this.$router.currentRoute.path,
              force: true,
            });
          });
      }
    },
  },
};
</script>

<style scoped>
.share {
  margin: 20px 0;
  margin-left: 10px;
}
.share textarea {
  height: 100px;
  width: 95%;
  border: solid 1px white;
  background-color: #17202A;
  border-radius: 5px;
  margin-top: 20px;
  resize: none;
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