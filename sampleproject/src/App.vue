<template>
  <div id="app">
    <div class="block_logo">
      <img id="logo" alt="Vue logo" src="./assets/MainLogo.png" />
      <p id="title">ESM Sample</p>
    </div>
    <Container msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import Container from "./components/Container.vue";

export default {
  name: "App",
  components: {
    Container,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  box-sizing: border-box;
}

#logo {
  width: 128px;
}

#title {
  font-size: 24px;
  color: #46505bb1;
  font-family: cursive;
}

.block_logo {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 64px;
}

@media (max-width: 640px) {
  #logo {
    width: 64px;
  }

  #title {
    font-size: 16px;
    color: #46505bb1;
    font-family: cursive;
  }

  .block_logo {
    justify-content: left;
    align-items: flex-end;
    margin-bottom: 24px;
  }

  #app {
    margin-top: 24px;
  }
}
</style>
