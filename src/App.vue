<template>
  <div id="app">
    <BugHeader :saveBugsCallBack="saveBugsCallBack"></BugHeader>
    <BugList :bugs="bugs" :solveBugCallBack="solveBugCallBack" :delBugCallBack="delBugCallBack"
      :checkAllCallBack="checkAllCallBack">
    </BugList>

    <BugFooter :bug_total="bugs.length" :bug_solved="bug_solved" :cleanSolvedBugsCallBack="cleanSolvedBugsCallBack">
    </BugFooter>
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
        { id: 0, detail: '界面显示问题0', checked: true },
        { id: 1, detail: '界面显示问题1', checked: true },
        { id: 2, detail: '界面显示问题2', checked: false },
        { id: 3, detail: '界面显示问题3', checked: true },
        { id: 4, detail: '界面显示问题4', checked: true },
        { id: 5, detail: '界面显示问题5', checked: false },
      ],
      isCheckedAll: false,      
    }
  },
  computed: {
    bug_solved() {
      let cnt = 0
      this.bugs.forEach(bug => {
        if (bug.checked) cnt++
      })
      return cnt;
    }
  },
  methods: {
    // 新增bug描述的回调函数
    saveBugsCallBack(bug) {
      bug.id = Date.now()
      bug.checked = false
      this.bugs.unshift(bug)
    },
    // 候选某个bug的回调函数
    solveBugCallBack(bugId) {
      for (let i = 0; i < this.bugs.length; i++) {
        if (this.bugs[i].id == bugId) {
          this.bugs[i].checked = !this.bugs[i].checked
          break;
        }
      }
    },
    // 点击全选的回调函数
    checkAllCallBack(val) {
      this.isCheckedAll = val
      this.bugs.forEach(bug => {
        bug.checked = val
      })
    },
    // 删除单个Bug的回调函数
    delBugCallBack(bugId) {
      for (let i = 0; i < this.bugs.length; i++) {
        if (this.bugs[i].id == bugId) {
          this.bugs.splice(i, 1)
          break;
        }
      }
    },
    // 清除已解决bug的回调函数
    cleanSolvedBugsCallBack() {
      let cnt = 0
      for (let i = this.bugs.length - 1; i >= 0; i--) {
        let bug = this.bugs[i]
        if (!bug.checked && cnt > 0) {
          this.bugs.splice(i + 1, cnt)
          cnt = 0
        } else if (bug.checked) {
          cnt++
        }
      }
      if (cnt > 0) this.bugs.splice(0, cnt)
    }
  }
}
</script>

<style>
button {
  cursor: pointer;
}
</style>
