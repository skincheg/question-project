<template>
  <div class="header">
    <router-link to="/1"
      ><img src="https://unimeal.com/images/logo.svg" alt="Logo"
    /></router-link>
    <router-link to="/"
      ><img src="https://unimeal.com/icons/nav_menu.svg" alt="Logo"
    /></router-link>
  </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.header {
  width: 100%;
  height: 72px;
  padding: 0 40px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

@media (max-width: 540px) {
  .header {
    padding: 0;
  }
}
</style>
