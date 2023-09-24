<template>
    <div class="search">
        <div class="search-bar">
            <input type="text" placeholder="请输入城市名字" v-model="cityName" class="search-input">
        </div>
        <div class="search-btn">
            <img id="search-icon" src="../../assets/weather-case/搜索.svg">
            <!-- <button>搜索</button> -->
        </div>

    </div>
</template>

<script>
export default {
    data() {
        return {
            cityName: '',
        }
    }
}
</script>

<style>
.search{
    display: flex;
    align-items: center;
    justify-content: space-evenly;
    padding: 25px 10px;

}
.search-btn{
    width: 50px;
    height: 50px;
    background-color: white;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    cursor: pointer;
}
.search-input {
    height: 50px;
    width: 340px;
    border-radius: 25px;
    padding-left: 20px;
    font-size: 17px;
    border: 1px solid #eee;
}

button {
    width: 55px;
    height: 50px;
    background-color: #1677ff;
    border: none;
    border-radius: 100%;
    color: #fff;
    font-size: 15px;
    font-weight: 600;
}

#search-icon {
    width: 30px;
}
</style>