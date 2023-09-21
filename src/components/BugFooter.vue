<template>
  <div class="footer">
    <button @click="cleanSolvedBugs">清除已解决</button>
    <span>当前Bug总量{{ bug_total }}个，已解决{{ bug_solved }}个</span>
  </div>
</template>

<script>
export default {
  props: {
    bug_total: {
      type: Number,
      default: 0
    },
    bug_solved: {
      type: Number,
      default: 0
    },
    cleanSolvedBugsCallBack: {
      type: Function
    }
  },
  methods: {
    cleanSolvedBugs() {
      if(confirm('确定清除所有已解决bug吗？'))
        this.cleanSolvedBugsCallBack();
    }
  },

}
</script>

<style scoped>
.footer {
  margin-left: 10px;
  color: #909399;
  font-size: 13px;
}

button {
  width: 110px;
  height: 40px;
  background-color: #67C23A;
  border: none;
  border-radius: 5px;
  color: #fff;
  font-size: 15px;
  font-weight: 600;
  margin: 20px;
}
</style>