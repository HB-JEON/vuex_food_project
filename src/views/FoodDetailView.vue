<template>
  <div>
    <div class="container">
      <div class="row">
        <table class="table">
          <tbody>
          <tr>
            <td width="30%" class="text-center" rowspan="8">
              <img :src="'https://www.menupan.com'+foods.food_detail.poster" style="width: 240px;height: 280px;">
            </td>
            <td colspan="2">
                <h3>{{ foods.food_detail.name }}&nbsp;
                    <span style="color: orange;">{{ foods.food_detail.score }}</span>
                </h3>
            </td>
          </tr>
          <tr>
            <th width="15%">주소</th>
            <td width="55%">{{ foods.food_detail.address }}</td>
          </tr>
          <tr>
            <th width="15%">전화</th>
            <td width="55%">{{ foods.food_detail.phone }}</td>
          </tr>
          <tr>
            <th width="15%">음식 종류</th>
            <td width="55%">{{ foods.food_detail.type }}</td>
          </tr>
          <tr>
            <th width="15%">주차</th>
            <td width="55%">{{ foods.food_detail.parking }}</td>
          </tr>
          <tr>
            <th width="15%">영업 시간</th>
            <td width="55%">{{ foods.food_detail.time }}</td>
          </tr>
          <tr>
            <th width="15%">테마</th>
            <td width="55%">{{ foods.food_detail.theme }}</td>
          </tr>
         </tbody>
        </table>
        <table class="table">
          <tr>
            <td>{{ foods.food_detail.content }}</td>
          </tr>
        </table>
      </div>
    </div>
  </div>
</template>
<script setup>
import { onMounted } from 'vue'
import { useFoodStore } from '@/stores/foods'
import { useRoute } from 'vue-router'
    
    const route = useRoute()
    const foods = useFoodStore()
    onMounted(() => {
      foods.foodDetailData(route.params.fno)
    })
</script>
<style>
.container {
    margin-top: 50px;
}
.row {
    margin: 0px auto;
    width: 800px;
}
</style>