<template>
  <section class="container">

    <a href="/users"> Ancor here</a>
    <router-link to="/users">Router_link</router-link>
    <nuxt-link to="/users">Nuxt_link</nuxt-link>

    <p>Another way to get to a page</p>
    <input type="text" v-model="userId">
    <button @click="onLoadUser"> Let's Go</button>


    <button @click="loadUser(1)">User 1</button>
    <button  @click="loadUser(2)">User 2</button>


  </section>
</template>

<script>
  export default {
    name: "userId",
    components: {},
    data() {
      return {
        userId: ''
      }
    },
    methods: {
      onLoadUser() {
        // non named route
        this.$router.push('/users/' + this.userId)
      },
      loadUser(id){

        // NAMED ROUTE take to same page as onLoadUser
        this.$router.push({name: "users-id", params: {id : id}})
      }
    }
  }
</script>

<style>
  .container {
    display: flex;
    flex-direction: column;
    margin: 0 auto;
    min-height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .title {
    font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
    display: block;
    font-weight: 300;
    font-size: 100px;
    color: #35495e;
    letter-spacing: 1px;
  }

  .subtitle {
    font-weight: 300;
    font-size: 42px;
    color: #526488;
    word-spacing: 5px;
    padding-bottom: 15px;
  }

  .links {
    padding-top: 15px;
  }
</style>
