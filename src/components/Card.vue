<template>
  <a href="#">
    <h1>{{ user.name }}</h1>
    <span> {{ user.email }} </span>
    <slot></slot>
  </a>
</template>
<script>
export default {
  props: ['user'],
};
</script>
