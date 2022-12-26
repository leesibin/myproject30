<template>
  <div>
    변수 머스타치 사용하기
    <h1>안녕하세요.이름은{{ vname }}이고.{{ age }}살 입니다.</h1>
    <h3>v-on버튼 기능사용하기</h3>
    <button v-on:click="func('안녕 팝업이야')">클릭버튼</button>
    <button v-on:click="func('안녕 또팝업이야')">더블클릭버튼</button>
    <hr>
    <h3>v-if조건문</h3>
    <h1 v-if="status">제가제가보이나요?</h1>
    <h1 v-show="status">제가 보이나요?</h1>
    <button v-on:click="status = true">보이게 할게요.</button>
    <button v-on:click="status = false">안보이게 할게요.</button>
    <button v-on:click="status = !status">보이면숨기고 안보이면 보이게</button>
    <hr>
    <h3>v-model 양방향데이터</h3>
    <input type="text" v-model="inData" v-on:keyup="func(inData + '적고손땜요!')">
    <input type="text" v-model="inData" v-on:keyup.enter="func(inData + '적고손땜요!')">
    <h2>{{ inData }}</h2>
  </div>
  <hr>
  <h3>v-for사용하기 /배열 : {{ arrData }}</h3>
  <button v-on:click='add'>추가하기</button>
  <button v-on:click='sub'>삭제하기</button>
  <ul>
    <li v-for="data in arrData" :key="data">{{ data }}</li>
  </ul>
  <P>추가한 값:{{ anum }}</P>
  <P>삭제한 값:{{ dnum }}</P>
  <hr>
  <h3>구구단</h3>
  <input type="text" v-model="gugu" v-on:keyup.enter="bdd()">
  <button v-on:click="bdd">열려라 참깨!</button>
  <button v-on:click="bub">닫아라 참깨!</button>
  <br>
  <span v-for="data0 in guguData" :key="data0">{{ data0 }} </span>
  <p>몇단이죠?{{ guguanum }}</p>
</template>

<script>
export default {
  name: 'app',
  data() {
    return {
      vname: '김수환',
      age: 60,
      status: false,
      inData: '',
      arrData: [],
      dnum: '',
      anum: '',
      gugu: '',
      guguData: [],
      guguanum: '',

    }
  },
  methods: {
    func: function (text) {
      alert(text)
    },
    add: function () {
      this.arrData.push(this.arrData.length + 1)
      this.anum = this.arrData.length
      this.dnum = ' '
    },
    sub: function () {
      this.dnum = this.arrData.pop()
      this.anum = ''
    },
    bdd: function () {
      this.guguData.push(this.gugu * 1,
        this.gugu * 2,
        this.gugu * 3,
        this.gugu * 4,
        this.gugu * 5,
        this.gugu * 6,
        this.gugu * 7,
        this.gugu * 8,
        this.gugu * 9)
      this.guguanum = this.gugu + '단'
      this.gugu = ''
    },
    bub: function () {
      this.gugu = ''
      this.guguData.splice(0);
      this.guguanum = this.guguData.splice(0);

    }
  }
}
</script>

<style>
ul {
  display: flex;
  margin: 0;
}

li {
  position: relative;
  margin: 0 20px;
}

li>text {
  margin-left: -3px;
}
</style>
