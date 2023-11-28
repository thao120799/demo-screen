<script setup>
import PatientList from '@/views/pages/tables/PatientsList.vue'
</script>

<template>
  <div>
    <VRow>
      <VCol
        cols="12"
        md="12"
      >
        <!-- 👉 Vertical Form with Icons -->
        <VCard>
          <VCardText>
            <VRow>
              <VCol class="d-flex ustify-start">
                <h1>患者情報管理</h1>
              </VCol>
              <VCol class="d-flex justify-end">
                <RouterLink
                  to="/patients-register-form"
                >
                <VBtn absolute right style="font-size: large;">追加</VBtn>
                </RouterLink>
                
              </VCol>
            </VRow>
          </VCardText>
          <VCardText>
            <PatientList />
          </VCardText>
        </VCard>
      </VCol>
    </VRow>
  </div>
</template>
