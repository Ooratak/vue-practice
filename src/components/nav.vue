<template>
  <div id>
    <ul>
      <li><router-link to="/" exact>Home</router-link></li>
      <li><router-link to="/about" exact>About</router-link></li>
      <li><router-link to="/form" exact>Form</router-link></li>
    </ul>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>

<style scoped>
  li {
    color: aliceblue;
    background-color: rgb(8, 4, 105);
    width: 80px;
    margin: 5px;
    border-radius: 5px;
    padding-top: 10px;
    padding-bottom: 10px;
    display: inline-block;
    text-align: center;
  }
  a {
    color: aliceblue;
    text-decoration: none;
  }
  a:hover {
    color: rgb(8, 4, 105);
    text-decoration: none;
  }
  li:hover {
    color: aliceblue;
    background-color: rgb(46, 43, 123);
    cursor: pointer;
  }
  ul {
    text-align: center;
  }
  .router-link-active {
    color: rgb(9, 139, 159);
  }
</style>