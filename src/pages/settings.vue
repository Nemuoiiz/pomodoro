<template>
  <v-container>
    <v-row>
      <v-col cols="12">
        <h1 class="text-center">鈴聲設定</h1>
      </v-col>
      <v-col cols="12">
        <v-table class="custom-table">
          <thead>
            <tr>
              <th>名稱</th>
              <th>試聽</th>
              <th>選擇</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="alarm in settings.alarms" :key="alarm.id">
              <td>{{ alarm.name }}</td>
              <td>
                <audio :src="alarm.file" controls></audio>
              </td>
              <td>
                <v-radio-group v-model="settings.selected" hide-details>
                  <v-radio :value="alarm.id"></v-radio>
                </v-radio-group>
              </td>
            </tr>
          </tbody>
        </v-table>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { useSettingsStore } from '@/stores/settings'
// 方法1️⃣ 定義頁面 title
// import { definePage } from 'vue-router/auto'
// definePage({
//   meta: {
//     title:'設定'
//   },
// })

const settings = useSettingsStore()

</script>

<style>
.custom-table {
  background-color: #9D9285 !important;
  border-radius: 10px !important;
}
</style>

<!-- 方法2️⃣ 使用 json 格式定義頁面 title -->
<!-- <route lang="json">
{
  "meta":{
    "title":"設定"
  }
}
</route> -->

<!-- 方法3️⃣ 使用 yaml 格式定義頁面 title -->
<route lang="yaml">
  meta:
    title: 設定
</route>
