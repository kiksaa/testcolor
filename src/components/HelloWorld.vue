<template>
  <div class="about">
    <!-- <div class="form-group">
      <label>Username</label>
      <input type="text" class="form-control" v-model="user.username">
    </div>
    <div class="form-group">
      <label>Mail</label>
      <input type="text" class="form-control" v-model="user.mail">
    </div>
    <button class="btn btn-primary" @click="submit">Submit</button> -->
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      user: {
        color: ""
      }
    };
  },
  methods: {
    submit() {
      console.log(this.user);
      let uri = "https://testcolor-dc933.firebaseio.com/data.json";
      axios.post(uri, this.user).then(response => {
        console.log(response);
      });
    }
  },
  mounted() {
    axios({
      method: "GET",
      url: "http://jsonplaceholder.typicode.com/todos"
    }).then(result => {
      console.log(result);
      this.httpdata = result.data;
    });
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
