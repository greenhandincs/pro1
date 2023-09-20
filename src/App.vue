<template>
  <div id="app">
    <BugHeader></BugHeader>
    <BugList></BugList>
    <BugFooter></BugFooter>
  </div>
</template>

<script>
import BugHeader from './components/BugHeader.vue';
import BugFooter from './components/BugFooter.vue';
import BugList from './components/BugList.vue';
export default {
  components:{BugHeader, BugFooter, BugList}
}
</script>

<style>
button {
  cursor: pointer;
}
</style>
