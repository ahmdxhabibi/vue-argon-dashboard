<template>
  <div>
    <p
      class="text-light p-3 bg-danger bg-opacity-10 border border-info border-start-0 rounded-end"
    >
      Are you sure you delete this ?
    </p>
    <button class="btn btn-danger" @click="deleteUser()">Delete</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  methods: {
    async deleteUser() {
      let a = window.confirm("You want to delete the user?");
      if (a) {
        const user = await axios.delete("https://reqres.in/api/users/2");
        console.log(user);
        alert("User deleted!");
      }
    },
  },
};
</script>
