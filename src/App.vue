<template>
  <div class="app">
    <header class="header">
      <router-link :to="{ path: '/' }" class="header__link">
        <h1>Star Wars people list</h1>
      </router-link>
    </header>
    <router-view />
  </div>
</template>

<style lang="scss">
body {
  margin: 0;
  background: #000;
  color: #fff;
  font-family: Arial, Helvetica, sans-serif;
}
.header {
  text-align: center;
  text-transform: uppercase;
  &__link {
    color: #fcd711;
    text-decoration: none;
  }
}
</style>
