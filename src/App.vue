<template>
  <div id="app">
    <header class="header">
      <h1>Sample project using Vue-CLI</h1>
    </header>
    <div class="nav">
      <router-link to="/">
        Home
      </router-link> |
      <router-link to="/about">
        About
      </router-link> |
      <router-link to="/films">
        Films
      </router-link> |
      <router-link to="/people">
        People
      </router-link>
    </div>
    <router-view />
    <footer class="footer">
      Copyright © 2019 by Irfan Maulana & Wisnu Dwi Hidayat
    </footer>
  </div>
</template>

<style lang="less">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: aqua;
}

.nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: red;
    }
  }
}

.footer{
  padding: 2em;
  margin: 0 auto;
  width: 100%;
  text-align: center;
}
</style>
