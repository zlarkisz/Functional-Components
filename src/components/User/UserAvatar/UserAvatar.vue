<template>
  <figure class="avatar">
    <img :src="user.avatar" :alt="user.name">
    <button @click.stop="listeners.contact">Contact me</button>
  </figure>
</template>

<script>
  export default {
    name: 'UserAvatar',

    props: {
      user: {
        type: Object,
      },
    },
  }
</script>