<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> <!-- | -->
      <!-- <router-link to="/about">About</router-link> -->
    </div>
    <router-view/>
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: #343F55;
  color: #F5E6CC;
}

.titlePage{
  color: #ED554D;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #F5E6CC;

    &.router-link-exact-active {
      color: #F5E6CC;
    }
  }
}

</style>
