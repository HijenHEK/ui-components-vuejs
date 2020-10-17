<template>
  <div id="app">
    <div id="nav" :class="{'nav-hidden' : navHidden}">
      
      <div class="nav-toggler" @click="navHidden = !navHidden">
          <font-awesome-icon icon="times"  v-if="!navHidden"/>
          <font-awesome-icon icon="bars"  v-else/>
      </div>
      <router-link to="/"> Home </router-link> 
      <router-link to="/Menus"> Collapsible menus </router-link>
    </div>
    <router-view class="view" :class="{'view-shrink' : !navHidden}" />
  </div>
</template>
<script>
export default {
  data() {
    return {
      navHidden : true 
    }
  },
}
</script>
<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
p {
    font-size: 1.5rem;
  }
  h1 {
    margin-bottom: 5rem ;
  }
body {
    background-color: #f3f3f3;

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  background-color: #f3f3f3;

}

#nav {
  padding: 1rem;
  width: 15rem;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: stretch;
  align-items: stretch;
  background-color: #ececec;
  box-shadow: 2px 2px 4px #ececec ;
  position: absolute;
  top:0 ;
  z-index: 1000;
  transition: all 0.3s ease-in-out;

}
.view {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 2rem   3rem;
  transition: all 0.3s ease-out;

}

.nav-toggler {
  margin-left: auto;
  cursor: pointer;
  font-size: 1.5rem;
}
#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.nav-hidden {
  flex: 0.15;
  position: relative;
  transform: translateX(-80%);

}


@media (min-width: 1000px) {
  
  .view-shrink{
    width: calc(100% - 15rem);
    margin-left:15rem ;
    transition: all 0.3s ease;
  }
}


</style>
