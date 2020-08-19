<template>
  <div>
    <p>UserList</p>
    <small v-for="user in users" :key="user.id">{{ user.name }} /</small>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";
export default {
  created() {
    this.getUSers();
  },
  computed: {
    ...mapState({ users: (state) => state.user.users }),
    //or
    // ...mapState('user'{ users: (state) => state.users }),
    //or
    ...mapState("user", ["users"]),
    // users() {
    //   return this.$store.state.users
    // },
  },
  methods: {
    ...mapActions("user", ["getUSers"]),

    //   getUSers() {
    //     //   //axios will return promise
    //     //   axios.get("https://jsonplaceholder.typicode.com/users").then((res) => {
    //     //     this.users = res.data
    //     //   })
    //     this.$store.dispatch("getUsers")
    //     //we got a payload so, don't need to second arguments
    //   },
  },
};
</script>
