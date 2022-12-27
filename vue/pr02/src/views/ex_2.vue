<template>
  <div>
    <h1>2. 데이터 가져오기</h1>
    <h4>가져온 데이터</h4>
    <p>{{ dataArr }}</p>
    <table>
      <tr>
        <th>카테고리</th>
        <th>품명</th>
        <th>가격</th>
        <th>배송비</th>
      </tr>
      <template v-for="item in dataArr" :key="item">
        <tr v-if="item.price >= inUser">
          <td>{{ item.category }}</td>
          <td>{{ item.product_name }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.delivery_price }}</td>
        </tr>
      </template>
      <!-- 위는 강사님이 알려주신 편법.
      아래의 검색창을 위해 template과 v-for, v-if를 사용했다. -->
    </table>
    <hr />
    <span>얼마 이상의 물품을 출력할까요?</span>
    <input type="text" v-model="inUser" />
    <!-- 입력하는 값 이상인 물품만 실시간으로 출력한다. -->
  </div>
</template>

<script>
import data from '../assets/productData.js'
/* 우리가 만든 js 땡겨오기. */
export default {
  name: 'app',
  data() {
    return {
      dataArr: data,
      /* 땡겨온 데이터 서버에 사용하기 */
      inUser: 0
    }
  },
  methods: {}
}
</script>

<style>
table {
  text-align: center;
  margin: auto;
  border-collapse: collapse;
}
th,
td {
  border: 1px solid #000;
}
</style>
