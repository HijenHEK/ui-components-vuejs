<template>
  <div id="app">
    <div id="nav">

      <router-link to="/"> Home </router-link> 
      <router-link to="/Menus"> Collapsible menus </router-link>
    </div>
    <router-view id="view"/>
  </div>
</template>

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
  height: 100vh;
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
  flex: 0.15;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: stretch;
  align-items: stretch;
  background-color: #ececec;
  box-shadow: 2px 2px 4px #ececec ;

}
#view {
  flex : 0.85;
  height: 100%;
  display: flex;
  flex-direction: column;
  padding: 2rem 1rem;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
