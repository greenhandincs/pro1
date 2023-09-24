<template>
  <div id="app2">
    <Search></Search>
    <Weather></Weather>
  </div>
</template>

<script>
import Search from './components/case2/Search.vue'
import Weather from './components/case2/Weather.vue'
export default {
    components: {Search, Weather}

}
</script>

<style>
#app2 {
    height: 600px;
    width: 550px;
    text-align: center;
    /* background: #bed8ee; */
    background: linear-gradient(to bottom right, #bed8ee, #419ef0);
    /* background: linear-gradient(to right, #ff0000, #00ff00); */
    border-radius: 4%;
}

</style>