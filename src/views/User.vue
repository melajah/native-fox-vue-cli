<template>
  <div>
    <h1>Users</h1>

    <FormUser @pushUser="addUser" />

    <div v-if="isLoadUser">loading...</div>
    <div v-else style="display:flex; flex-direction: row">
      <div>
        <ul>
          <li v-for="user in users" :key="user.id" @click="getUser(user)">
            <Card :user="user" />
          </li>
        </ul>
      </div>
      <div>
        Halaman detail
        <Card v-if="user" :user="user">
          <p>{{ user.username }}</p>
        </Card>
      </div>
    </div>
  </div>
</template>
<script>
import Card from '@/components/Card.vue';
import FormUser from '@/components/FormUser.vue';
import { apiUrl } from '@/utils';

export default {
  name: 'User',
  data() {
    return {
      users: [],
      isLoadUser: true,
      user: null,
    };
  },
  components: {
    Card,
    FormUser,
  },
  methods: {
    getUsers() {
      fetch(`${apiUrl}/users`)
        .then((response) => response.json())
        .then((users) => {
          this.users = users;
          this.isLoadUser = false;
        })
        .catch(console.log);
    },
    getUser(user) {
      console.log(user);
      this.user = user;
    },
    addUser(payload) {
      console.log(payload);
      this.users.push(payload);
    },
  },
  mounted() {
    this.getUsers();
  },
};
</script>
