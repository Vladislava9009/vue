<template>
  <div id="app">
     <div class="menu">
          <div class="item">
                <img src="./images/logo.png" alt="Logo">
           </div>
           <div class="item">
             <img src="./images/menu.png" alt="menu">
           </div>
       </div>
<app-Catalog></app-catalog>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
  
}
</script>

<style>
body{
  margin:0;
}
.menu{
background: #31333B;
display:flex;

}
.item{
  color:white;
  margin:1%;
}
</style>
