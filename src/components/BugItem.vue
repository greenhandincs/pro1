<template>
    <tr>
        <td class="tb-select"><input type="checkbox" @change="handleChecked" :checked="bug.checked"></td>
        <td class="tb-info">{{ bug.detail }}</td>
        <td class="tb-del"><button @click="delBug">删除</button></td>
    </tr>
</template>

<script>
export default {
    props: ['bug', 'solveBugCallBack', 'delBugCallBack'],
    methods: {
        handleChecked(){            
            this.solveBugCallBack(this.bug.id)                        
        },
        delBug() {
            if(confirm('确定要删除Bug吗')) {
                this.delBugCallBack(this.bug.id)                

            }
        }
    }
}
</script>

<style scoped>
.tb-select {
    width: 80px;
}

.tb-del {
    width: 100px;
}

td {
    border: 1px solid #ebebeb;
}

tr {
    height: 40px;
}
button {
    width: 60px;
    height: 25px;
    background-color: #1677ff;
    border: none;
    border-radius: 5px;
    color: #fff;
    font-size: 14px;    
}
</style>