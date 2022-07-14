<template>
  <div id="app">
    <!-- <UserAvatarFunctional :avatar="user.avatar" /> -->

    <UserAvatar :user="user" />

    <!-- <ListWrapper listType="ul">
      <li>Wonder Woman</li>
      <li>Batman</li>
      <li>Superman</li>
      <li>Aquaman</li>
    </ListWrapper>

    <ListWrapper listType="ol">
      <li>Wonder Woman</li>
      <li>Batman</li>
      <li>Superman</li>
      <li>Aquaman</li>
    </ListWrapper> -->
    <h1>User Card</h1>

    <div class="center">
      <UserCard
        :user="user"
        @click="nameAlert(user.name)"
        @contact="contactUser(user.name)"
      >
        <strong>{{ user.bio }}</strong>
      </UserCard>
    </div>
  </div>
</template>

<script>
import UserCard from '@/components/User'
// import ListWrapper from '@/components/ListWrapper.vue'
// import UserAvatarFunctional from '@/components/User/UserAvatar'
import UserAvatar from '@/components/User/UserAvatar/UserAvatar.vue'

export default {
  name: 'App',

  components: {
    UserCard,
    // ListWrapper
    // UserAvatarFunctional,
    UserAvatar
  },

  data() {
    return {
      user: {
        name: 'Jane Doe',
        role: 'Staff Engineer',
        avatar: 'https://randomuser.me/api/portraits/women/26.jpg',
        bio:
          'Candy canes sweet roll pudding liquorice jelly beans brownie powder pie. Pudding powder marshmallow sugar plum dessert pastry jelly-o pastry marzipan. Jelly topping biscuit jelly beans cookie cheesecake.',
      },
    };
  },

  methods: {
    nameAlert(name) {
      alert(`Clicked on ${name}`)
    },

    contactUser(name) {
      alert(`Contacting ${name}`)
    }
  },

    created () {
      console.time('rendering');
    },

    mounted () {
      console.timeEnd('rendering');
    },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
