

<template>
  <main>
    <title>Random User Generator</title>
    <img :class="gender" :src="picture" :alt="firstName"/>
    <h1>Hello {{firstName}} {{lastName}}</h1>
    <h3>Email: {{email }}</h3>
    <button :class="gender">Get Random User</button>
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