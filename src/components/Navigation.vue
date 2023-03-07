<template>
  <div class="navbar">
    <nav class="nav">
      <span class="logo">Reaction Test</span>
      <ul>
        <li><a>Test</a></li>
        <li><a>Results</a></li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.nav {
  height: 60px;
  background: azure;
  box-shadow: 1px 1px 3px rgba(0, 0, 0, 0.2);
  display: flex;
  justify-content: space-around;
  align-items: center;
}

.nav ul {
  display: inline-block;
  list-style-type: none;
}

.logo {
  float: left;
  color: teal;
  font-weight: bold;
}

li {
  display: inline;
  float: right;
  margin-left: 30px;
}

a {
  display: block;
  padding: 8px;
  color: teal;
}
</style>
