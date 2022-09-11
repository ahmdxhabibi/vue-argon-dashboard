<template>
  <form>
    <div class="user-update">
      <h2>Update user</h2>
      <div class="mb-3">
        <label class="form-label">Name</label>
        <input class="form-control" type="text" v-model="name" />
      </div>
      <div class="mb-3">
        <label class="form-label">Job</label>
        <input class="form-control" type="text" v-model="job" />
      </div>
      <button class="btn btn-primary" @click="updateUser">Update</button>
    </div>
  </form>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      name: "",
      job: "",
    };
  },
  methods: {
    async updateUser() {
      try {
        const user = await axios.put("https://reqres.in/api/users/2", {
          name: this.name,
          job: this.job,
        });
        console.log(user);
        alert("User updated!");
      } catch (e) {
        console.log(e);
      }
    },
  },
};
</script>
