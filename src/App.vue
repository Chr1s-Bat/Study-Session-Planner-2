<script setup>
</script>

<template>
  <div id="app">
    <nav class="navbar">
      <router-link to="/">Home</router-link>
      <router-link to="/study-sessions">Study Sessions</router-link>
      <router-link to="/about">About</router-link>
    </nav>
    <main>
      <router-view />
    </main>
  </div>
</template>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f6f8;
  color: #333;
}
.navbar {
  background-color: #2c3e50;
  padding: 1rem;
  display: flex;
  gap: 1.5rem;
}
.navbar a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}
.navbar a.router-link-active {
  color: #42b883;
}
</style>