<template>
  <div class="weather">
    <!-- <h1>天气</h1> -->
    <div class="weather-icon">
      <img src="../../assets/weather-case/多云.svg" alt="多云">
    </div>
    <div class="desc">
      <div class="temperature">
        {{ temprature }}℃
      </div>
      <div class="city">
        {{ city }}
      </div>
    </div>
    <div class="detail">
      <!-- 湿度 -->
      <div class="sub-detail">
        <div class="sub-detail-icon">
          <i class="iconfont icon-shidu"></i>
        </div>
        <div class="sub-detail-text">
          {{ humidity }}%
          <div class="tips">湿度</div>
        </div>
      </div>
      <!-- 风速 -->
      <div class="sub-detail">
        <div class="sub-detail-icon">
          <i class="iconfont icon-fengsu"></i>
        </div>
        <div class="sub-detail-text">
          {{ windSpeed }}米/秒
          <div class="tips">风速</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import 
export default {
  data() {
    return {
      temprature: 22,
      city: '北京',
      humidity: 50,
      windSpeed: 15
    }
  },
}
</script>

<style>
.iconfont {
  font-size: 50px;
  margin-right: 10px;
}

.weather-icon img {
  width: 150px;
}

.desc {
  color: white;
  /* font-weight: 600; */
}

.temperature {
  font-size: 60px;
}

.city {
  font-size: 50px;
}

.detail {
  display: flex;
  justify-content: space-evenly;
  margin: 60px 0;
}

.sub-detail {
  font-size: 25px;
  color: white;
  display: flex;
}

.tips {
  font-size: 18px;
}
</style>