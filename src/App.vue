<template>
  <h1>Hello World</h1>
  <table>
    <thead>
      <tr>
        <th>User</th>
      </tr>
      <tbody>
          <tr v-for="user in users" :key="user.id"> 
              {{ user.name }}
          </tr>
      </tbody>
    </thead>
  </table>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      users: [],
    };
  },
  async mounted() {
    const res = await fetch("https://jsonplaceholder.typicode.com/users");
    const data = await res.json();
    console.log(data);
    this.users = data;
  },
};
</script>

<style></style>
