<template>
  <div id="app">
    <BugHeader :saveBugsCallBack="saveBugsCallBack"></BugHeader>
    <BugList :bugs="bugs" 
            :solveBugCallBack="solveBugCallBack" 
            :delBugCallBack="delBugCallBack"
            :checkAllCallBack="checkAllCallBack"
    >
    </BugList>
    <BugFooter :bug_total="bugs.length" :bug_solved="bug_solved"></BugFooter>
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
        { id: 0, detail: '界面显示问题3', checked: false },
        { id: 1, detail: '界面显示问题1', checked: false },
        { id: 2, detail: '界面显示问题2', checked: false },
      ],
      isCheckedAll: false,
      bug_solved: 0
    }
  },
  //统计bug解决数量方法一
  // computed: {
  //   bug_solved() {
  //     let cnt = 0
  //     this.bugs.forEach(bug => {
  //       if(bug.checked) cnt++
  //     })
  //     return cnt;
  //   }
  // },
  methods: {
    saveBugsCallBack(bug) {
      bug.id = this.bugs.length
      bug.checked = this.isCheckedAll
      this.bugs.unshift(bug)
    },
    solveBugCallBack(bugId) {
      for(let i = 0; i < this.bugs.length; i++) {
        if(this.bugs[i].id == bugId) {          
          this.bugs[i].checked = !this.bugs[i].checked   
          // 统计bug解决数量方法二
          if(this.bugs[i].checked) this.bug_solved++;
          else this.bug_solved--;       
          break;
        }
      }
    },
    checkAllCallBack(val) {
      this.isCheckedAll = val
      this.bugs.forEach(bug => {
        bug.checked = val
      })
      this.bug_solved = val ? this.bugs.length : 0
    },
    delBugCallBack(bugId) {
      for(let i = 0; i < this.bugs.length; i++) {
        if(this.bugs[i].id == bugId) {   
          if(this.bugs[i].checked) this.bug_solved--;       
          this.bugs.splice(i, 1)      
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
