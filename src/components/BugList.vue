<template>
    <div id="bug-list">
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
    comments: { BugItem }

}
</script>

<style scoped>
#bug-list {
    margin: 40px 20px;
}

table {
    width: 600px;
    text-align: center;
    /* border: ; */
    border-collapse: collapse;
}

th,
td {
    
    border: 1px solid #ebebeb;
}

tr {
    height: 40px;
}
tr:nth-child(even) {
    background-color: #f2f4f7;
  }
</style>