<script setup>
import PatientsRegisterForm from '@/views/pages/form-layouts/PatientsRegisterForm.vue'
</script>

<template>
  <div>
    <VRow>
      <VCol
        cols="12"
        md="12"
      >
        <!-- 👉 Vertical Form with Icons -->
        <VCard title="患者情報登録">
          <VCardText>
            <PatientsRegisterForm />
          </VCardText>
        </VCard>
      </VCol>
    </VRow>
  </div>
</template>
