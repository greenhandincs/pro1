<template>
    <tr>
        <td class="tb-select"><input type="checkbox"></td>
        <td class="tb-info">{{ bugDetail }}</td>
        <td class="tb-del"><button>删除</button></td>
    </tr>
</template>

<script>
export default {
    props: ['bugDetail']
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