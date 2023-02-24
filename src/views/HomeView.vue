

<template>
  <main>
    <title>Random User Generator</title>
    <h1>Hello {{firstName}} {{lastName}}</h1>
    <h3>{{email }}</h3>
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
    }





  }
</script>