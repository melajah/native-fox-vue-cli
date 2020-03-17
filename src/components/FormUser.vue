<template>
  <div>
    <form>
      <div>
        <label for="name">name</label>
        <input type="text" id="name" v-model="form.name" />
      </div>
      <div>
        <label for="email">email</label>
        <input type="email" id="email" v-model="form.email" />
      </div>
      <div>
        <label for="username">Username</label>
        <input type="username" id="username" v-model="form.username" />
      </div>
    </form>
    <button @click="pushData">Add user</button>
  </div>
</template>
<script>
export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        username: '',
      },
    };
  },
  methods: {
    pushData() {
      console.log('asa');
      this.$emit('pushUser', this.form);
      this.form = {
        name: '',
        email: '',
        username: '',
      };
    },
  },
};
</script>
