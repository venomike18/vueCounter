

<template>
  <main>
    <title>Random User Generator</title>
    <img :class="gender" :src="picture" :alt="firstName"/>
    <h1>Hello {{firstName}} {{lastName}}</h1>
    <h3>Email: {{email }}</h3>
    <button v-on:click="getUser()" :class="gender">Random User</button>
    <button v-on:click="changeSex()" :class="gender">Change Sex</button>
    <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
    </nav>
  </main>
</template>


<script>
  export default {
    name: "HomeView",
    data(){
      return{
        firstName: 'Jhon',
        lastName: 'Doe',
        email: 'john@gmail.com',
        gender: 'male',
        picture: 'https://randomuser.me/api/portraits/men/10.jpg',
      }
    },
    methods:{
      async getUser(){
        const res = await fetch('https://randomuser.me/api')
        const { results } = await res.json()

        this.firstName = results[0].name.first
        this.lastName = results[0].name.last
        this.email = results[0].email
        this.gender = results[0].gender
        this.picture = results[0].picture.large
      },
      changeSex(){
        if(this.gender== 'male'){
          this.gender = 'female'
          this.firstName = 'Maria'
          this.picture = 'https://randomuser.me/api/portraits/women/10.jpg'
        }else if(this.gender== 'female'){
          this.gender ='male'
          this.firstName = 'Mario'
          this.picture = 'https://randomuser.me/api/portraits/men/10.jpg'
        }
      },
    },
  }
</script>