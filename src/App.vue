<template>
  <nav>
    <div id="app">
      <div id="nav">
        <nav class="navbar bg-light">
          <div class="container-fluid">
            <a class="navbar-brand" href="#">
              <img
                src="/docs/5.2/assets/brand/bootstrap-logo.svg"
                alt="Logo"
                width="30"
                height="24"
                class="d-inline-block align-text-top"
              />
              Bootstrap
            </a>
          </div>
        </nav>

        <router-link to="/">Home</router-link> |
        <router-link to="/Login">Login</router-link>
      </div>
    </div>
  </nav>
  <router-view />
</template>
<script></script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
