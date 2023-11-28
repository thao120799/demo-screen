<script setup>
const patients = [];
for (let i = 0; i < 15; i++) {
  patients.push({
    id: i,
    name: "患者" + i,
    name_in_furigana: "kanja " + i,
    birthday: "1999-12-12",
    address: "abc",
    mail: "abc@gmail.com",
    phone_number: "080-2345-2321",
    insurance_company: "ABC",
    device_type: "ABC",
    disease_level: "none",
  });
}
</script>

<template>
  <VTable>
    <thead>
      <tr>
        <th><h2>お名前</h2></th>
        <th><h2>お名前（ふりがな）</h2></th>
        <th><h2>誕生日</h2></th>
        <th><h2>住所</h2></th>
        <th><h2>メール</h2></th>
        <th><h2>電話番号</h2></th>
        <th><h2>保健所</h2></th>
        <th><h2>機器端末</h2></th>
        <th><h2>重病度</h2></th>
      </tr>
    </thead>

    <tbody>
      <tr v-for="patient in patients" :key="patient.id">
        <td>
          {{ patient.name }}
        </td>
        <td class="text-center">
          {{ patient.name_in_furigana }}
        </td>
        <td class="text-center">
          {{ patient.birthday }}
        </td>
        <td class="text-center">
          {{ patient.address }}
        </td>
        <td class="text-center">
          {{ patient.mail }}
        </td>
        <td class="text-center">
          {{ patient.phone_number }}
        </td>
        <td class="text-center">
          {{ patient.insurance_company }}
        </td>
        <td class="text-center">
          {{ patient.device_type }}
        </td>
        <td class="text-center">
          {{ patient.disease_level }}
        </td>
      </tr>
    </tbody>

    
  </VTable>
</template>
