<template>
  <footer class="footer">
    <p>&copy; 2024 Online Store. All rights reserved.</p>
  </footer>
</template>

<script>
export default {
  name: 'Footer'
}
</script>

<style>
.footer {
  background-color: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
  width: 100%;
}

html, body {
  height: 100%;
  margin: 0;
}

#app {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}
</style>