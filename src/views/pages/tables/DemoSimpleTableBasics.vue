<script setup>
const desserts = [
  {
    dessert: 'ABC',
    calories: 159,
    fat: 6,
    carbs: 2023,
    protein: 4,
  },
  {
    dessert: 'DEF',
    calories: 237,
    fat: 6,
    carbs: 2023,
    protein: 4,
  },
]
</script>

<template>
  <VTable>
    <thead>
      <tr>
        <th class="text-uppercase">
          端末番号 
        </th>
        <th>
          患者番号
        </th>
        <th>
          数値
        </th>
        <th>
          更新日
        </th>
        <th>
          詳細情報
        </th>
      </tr>
    </thead>

    <tbody>
      <tr
        v-for="item in desserts"
        :key="item.dessert"
      >
        <td>
          {{ item.dessert }}
        </td>
        <td class="text-center">
          {{ item.calories }}
        </td>
        <td class="text-center">
          {{ item.fat }}
        </td>
        <td class="text-center">
          {{ '24-2-2022' }}
        </td>
        <td class="text-center">
          {{ item.protein }}
        </td>
      </tr>
    </tbody>
  </VTable>
</template>
