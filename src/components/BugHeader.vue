<template>
    <div>
        <div class="text">
            <textarea placeholder="请输入BUG描述信息" rows="5" cols="50" v-model="bugDetail"> </textarea>
        </div>
        <div class="btn">
            <button @click="submit">提交</button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            bugDetail: ''
        }
    },    
    props: ['saveBugsCallBack'],
    methods: {
        submit() {            
            if(!this.bugDetail.trim()) return
            const bug = {detail: this.bugDetail}
            this.saveBugsCallBack(bug)
            this.bugDetail = ''
        }
    }

}
</script>

<style scoped>
.text textarea {
    font-size: 20px;
    padding: 15px 20px;
}

textarea:focus {
    outline-color: #409EFF;
    border: 1px solid
}

.btn button {
    width: 100px;
    height: 35px;
    background-color: #1677ff;
    border: none;
    border-radius: 5px;
    color: #fff;
    font-size: 15px;
    font-weight: 600;
}
</style>