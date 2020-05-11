<template>
  <div id="app">
    <div id="nav">
            <router-link to="/">DevJokes</router-link>

    </div>
    <div id="img">
      <div id="opacity">
  
      </div>
    </div>
    <router-view/>
  </div>
</template>

<style>
* {
  margin: 0%;
  padding: 0%;
  
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #FfF;
  
}

#nav {
  height: 70PX;
  background-color: lightgrey;
  Position:fixed;
  z-index:8;
  width: 100%;
  height: 50px;
  color: white;
}

#nav a {
  font-weight: bold;
  color: white;
}

img {
  position: absolute;
  top: 2.5px;
  left: 5px;
}

#nav a.router-link-exact-active {
  position:absolute;
  color:  #000000;
  top: 16px;
  text-align:center;
  text-decoration: none;

}
#img{
  top:50px;
  width: 100%;
  height: 250px;
  position:relative;
  background-image: url("./assets/Banner.jpg");
  
}
#opacity{
  width: 100%;
  height: 100%;
  position:absolute;
  z-index:4;
  background-color: rgba(255, 255, 255,0.5);  
  
}
</style>
