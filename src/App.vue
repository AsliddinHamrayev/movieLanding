<template>
  <main>
    <div class="container">
      <div class="main-content">
        <Main />
        
        <New />

        <Show />
      </div>
    </div>
    <router-view />
  </main>
</template>
<script>
import Main from "./components/Main.vue";
import New from "./components/New.vue";
import Show from "./components/Show.vue";
export default {
  name: "app",
  components: {
    Main,
    New,
    Show,
  },    
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

.container {
  max-width: 1440px;
  margin: 0 auto;
}

.main-content {
  background-color: #1d1d1d;
}

body::-webkit-scrollbar {
  width: 5px;
}

body::-webkit-scrollbar-track {
  background-color: #fff;
}

body::-webkit-scrollbar-thumb {
  background-color: cornflowerblue;
}
</style>
