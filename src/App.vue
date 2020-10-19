<template>
  <div id="app">
    <div id="nav" :class="{'nav-hidden' : navHidden}">
      
      <div class="nav-toggler" @click="navHidden = !navHidden">
          <font-awesome-icon class="icon" icon="times"  v-if="!navHidden"/>
          <font-awesome-icon class="icon" icon="bars"  v-else/>
      </div>
      <router-link class="link" to="/">
          <div class="name">Home</div>
          <font-awesome-icon class="icon" icon="home" />
       </router-link> 
        <router-link class="link" to="/Menus">
          <div class="name">Menus and Lists</div>
          <font-awesome-icon class="icon" icon="bars" />
      </router-link>
      <router-link class="link" to="/Navbars">
        <div class="name">Responsive NavBars</div>
        <!-- <font-awesome-icon icon="ellipsis" /> -->
        <div class="icon">N</div>
      </router-link>
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
    color: rgb(1,56,112);

}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  background-color: #EDF5E1;

}
.view {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 2rem   3rem;
  transition: all 0.3s ease-out;
  margin-left:2rem ;

}
#nav {
  width: 15rem;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: stretch;
  align-items: flex-start;
  background-color: #65E191;
  box-shadow: 2px 2px 4px #65E191 ;
  position: absolute;
  top:0 ;
  z-index: 1000;
  transition: all 0.3s ease-in-out;
}


.nav-toggler {
  margin-left: auto;
  cursor: pointer;
  font-size: 1.5rem;
}
#nav .link {
  font-weight: bold;
  color: rgb(1,56,112);
  text-decoration: none;
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
  
}
#nav .link.router-link-exact-active {
  color:  #EBF6DE;
  background-color: #399583;
  box-shadow: 2px 2px 4px #399583 ;
  transition: all 0.2s ease-in-out;

}
#nav .link .icon {
    font-size: 1.5rem;
    max-width: 1.5rem;
    text-align: center;
}
#nav > * {
  padding: 1rem 0.7rem;

}
/* #nav a.router-link-exact-active {
} */

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
