<template>
  <div id="app">
    <div id="menu">
      <div id="brand">
        <router-link to="/">
          <img src="../public/images/logo.png" />
        </router-link>
      </div>
      <div id="side">
        <router-link to="/browse">
          <div class="menu-item browse">
            <img src="../public/images/globe.png" />
            <p>Browse</p>
          </div>
        </router-link>
        <router-link to="/cart">
          <div class="menu-item">
            <img src="../public/images/love.png" />
            <p>{{ getCartItems }} items</p>
          </div>
        </router-link>
      </div>
    </div>
    <router-view />

    <div class="github-container">
      <ul class="social-links">
        <li>
          <a
            href="https://github.com/BYUCS260/grocery-store-mgordillo11"
            target="blank"
            ><i class="fab fa-github"></i
          ></a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  computed: {
    getCartItems() {
      return this.$root.$data.cart.length;
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #b84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

.github-container {
  display: flex;
  justify-content: center;
  font-size: 100px;
}

.fab {
  color: black;
}

.github-container li {
  list-style: none;
}
</style>
