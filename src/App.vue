<template>
  <div id="app">
    <BugHeader :saveBugsCallBack="saveBugsCallBack"></BugHeader>
    <BugList :bugs="bugs" :solveBugCallBack="solveBugCallBack"></BugList>
    <BugFooter></BugFooter>
  </div>
</template>

<script>
import BugHeader from './components/BugHeader.vue';
import BugFooter from './components/BugFooter.vue';
import BugList from './components/BugList.vue';

export default {
  components: { BugHeader, BugFooter, BugList },
  data() {
    return {
      bugs: [
        { id: '001', detail: '界面显示问题', checked: false },
      ]
    }
  },
  methods: {
    saveBugsCallBack(bug) {
      bug.id = this.bugs.length
      this.bugs.unshift(bug)
    },
    solveBugCallBack(bugId) {
      for(let i = 0; i < this.bugs.length; i++) {
        if(this.bugs[i].id == bugId) {          
          this.bugs[i].checked = !this.bugs[i].checked          
          break;
        }
      }
    }
  }
}
</script>

<style>
button {
  cursor: pointer;
}
</style>
