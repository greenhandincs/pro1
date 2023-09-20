<template>
    <div>
        <table>
            <tr>
                <th>全选<input type="checkbox"></th>
                <th>Bug描述</th>
                <th>操作</th>
            </tr>
            <BugItem bug-detail="XXXX"></BugItem>
            <BugItem bug-detail="XXXX"></BugItem>
            <BugItem bug-detail="XXXX"></BugItem>          
        </table>
    </div>
  
</template>

<script>
import BugItem from './BugItem.vue';
export default {
  components: { BugItem },
    comments:{BugItem}

}
</script>

<style>

</style>