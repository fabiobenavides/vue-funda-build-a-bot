<template>
  <header>
    <nav>
      <ul>
        <li class="nav-item">
          <router-link :to="{name:'Home'}">
            <img class="logo" src="./assets/build-a-bot-logo.png"/>
            Home
          </router-link>
        </li>
        <li class="nav-item">
          <router-link :to="{name:'Build'}">
            Build-a-Bot
          </router-link>
        </li>
        <li class="nav-item cart">
          <router-link to="/Cart">
            Cart
          </router-link>
          <div class="cart-items">
            {{ cart.length }}
          </div>
        </li>
      </ul>
    </nav>
  </header>
  <div class="container">
    <aside class="aside">
      <router-view name="sidebar"/>
    </aside>
    <main>
      <router-view/>
    </main>
  </div>
</template>

<script>

export default {
  name: 'app',
  computed: {
    cart() {
      return this.$store.state.cart;
    },
  },
};
</script>

<style>
body {
  background: linear-gradient(to bottom, #555, #999);
  background-attachment: fixed;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>

<style scoped>

.container {
  display: flex;
  justify-content: center;
  margin: 10px auto 0 auto;
}
.aside {
  padding: 30;
  background-color: #aaa;
  width: 100px;
  min-height: 300px;
}
main {
  padding: 30px;
  background-color: white;
  width: 964px;
  min-height: 300px;
}
header {
  background-color: #999;
  width: 1184px;
  margin: 0 auto;
}
ul {
  padding: 3px;
  display: flex;
}
.nav-item {
  display: inline-block;
  padding: 5px 10px;
  font-size: 22px;
  border-right: 1px solid #bbb;
}
.nav-item.cart {
  position: relative;
  margin-left: auto;
  border-right: none;
}
.logo {
  vertical-align: middle;
  height: 30px;
}

.cart-items {
  position: absolute;
  top: -5px;
  right: -9px;
  font-size: 18px;
  width: 20px;
  text-align: center;
  display: inline-block;
  border-radius: 100px;
  background-color: mediumseagreen;
}

</style>
