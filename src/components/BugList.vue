<template>
    <div id="bug-list">
        <table>
            <tr>
                <th>全选<input type="checkbox" @change="checkAll" v-model="isCheckAll"></th>
                <th>Bug描述</th>
                <th>操作</th>
            </tr>
            <BugItem v-for="bug in bugs" :key="bug.id" :bug="bug" :solveBugCallBack="solveBugCallBack"
                :delBugCallBack="delBugCallBack" :changeCheckAllStautsCallBack="changeCheckAllStautsCallBack"></BugItem>
            <!-- <BugItem bug-detail="XXXX"></BugItem>
            <BugItem bug-detail="XXXX"></BugItem> -->
        </table>
    </div>
</template>

<script>
import BugItem from './BugItem.vue';
export default {
    components: { BugItem },
    props: ['bugs', 'solveBugCallBack', 'delBugCallBack', 'checkAllCallBack'],
    data() {
        return {
            isCheckAll: false
        }
    },
    updated() {
        let flag = true;     
        let n = this.bugs.length
        if(n == 0) {
            this.isCheckAll = false;
            return;
        }   
        for(let i = 0; i < this.bugs.length; i++) {
            if(!this.bugs[i].checked){
                flag = false;
                break;
            }
        }
        this.isCheckAll = flag;
    },
    methods: {
        checkAll() {
            this.checkAllCallBack(this.isCheckAll)
        },
        changeCheckAllStautsCallBack(status) {
            // console.log('status' + preStatus);
            if (!status && this.isCheckAll) { //原来被选中，现取消选中
                this.isCheckAll = false;
            } else if (status) { //原来没选，现在选中了
                let flag = true;
                this.bugs.forEach(bug => {
                    if (!bug.checked)
                        flag = false;
                })
                this.isCheckAll = flag;
            }
        }
    }

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