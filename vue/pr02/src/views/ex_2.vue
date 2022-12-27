<template>
  <div class="ex_2">
    <h1>2.데이터 가져오기</h1>
    <h4>가져온 데이터</h4>
    <p>{{ dataArr }}</p>
    <table>
      <tr>
        <th>카테고리</th>
        <th>품명</th>
        <th>가격</th>
        <th>배송비</th>
      </tr>
      <template v-for="item in dataARr" :key="item">
        <tr v-if="item.price > inUser">
          <td>{{ item.category }}</td>
          <td>{{ item.product_name }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.delivery_price }}</td>
        </tr>
      </template>
    </table>
    <hr />
    <span>얼마이상의 물품을 출력할까요?</span>
    <input type="text" v-model="inUser" />
  </div>
</template>

<script>
import data from '../assets/productData.js'
export default {
  name: 'app',
  data() {
    return {
      inUser: 0,
      dataArr: data
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
