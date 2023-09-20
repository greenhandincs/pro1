<template>
  <div>    
    <button>清除已解决</button>
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
    }

}
</script>

<style>

</style>