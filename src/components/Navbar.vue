<template>
  <div id="navbar">
    <ul>
      <li></li>
      <li><router-link to="/"> Home </router-link></li>
      <li><router-link to="/projects"> Projects </router-link></li>
      <li><router-link to="/resume"> Résumé </router-link></li>
      <li><router-link to="/about"> About </router-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Navbar"
}
</script>

<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333333;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #111111;
}

a.router-link-exact-active {
  background: #111111;
}
</style>