<script setup>
import DemoFormLayoutVerticalFormWithIcons from '@/views/pages/form-layouts/DemoFormLayoutVerticalFormWithIcons.vue'
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
            <DemoFormLayoutVerticalFormWithIcons />
          </VCardText>
        </VCard>
      </VCol>
    </VRow>
  </div>
</template>
