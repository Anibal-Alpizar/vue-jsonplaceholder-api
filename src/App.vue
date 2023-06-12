<template>
  <div class="container">
    <div class="row">
      <h1>Hello World!</h1>
      <input
        type="text"
        class="form-control bg-dark text-light rounded-0 border-0 my-4"
        placeholder="Search"
      />

      <table class="table table-dark">
        <thead>
          <tr>
            <th v-for="title in titles" :key="title">
              {{ title }}
            </th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="user in users" :key="user.id">
            <td>
              {{ user.id }}
            </td>
            <td>
              {{ user.name }}
            </td>
            <td>
              {{ user.username }}
            </td>
            <td>
              {{ user.email }}
            </td>
            <td>
              {{ user.address.street }}
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      users: [],
      titles: ["id", "name", "username", "email", "address"],
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
