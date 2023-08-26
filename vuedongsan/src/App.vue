<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <div>
    <h4>{{ products[0] }}</h4>
    <p>{{ price1 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[1] }} </h4>
    <p>{{ price2 }} 만원</p>
  </div>
  <div>
    <h4>{{ products[2] }} </h4>
    <p>{{ price3 }} 만원</p>
  </div>

</template>

<script>

// {{데이터바인딩}} 하는 이유 : Vue의 실시간 자동 렌더링. 웹앱

export default {
  name: 'App',
  data() {
    return {
      // 데이터 보관함 object 자료
      price1 : 60,
      price2 : 70,
      price3 : 70,
      products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
    }
  },
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
