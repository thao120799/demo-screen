<script setup>
const metrics = [];
let date = new Date();
for (let i = 0; i < 50; i++) {
    metrics.push({
    patient_id: "患者" + i,
    device_id: "ABC " + i,
    time: date.getDate() + "/" + date.getMonth() + "/" + date.getFullYear() + " " + date.getHours() + ":" + date.getMinutes().toString().padStart(2, '0'),
    SpO2: 90 + Math.floor(Math.random() * 10),
    PR: 100  + Math.floor(Math.random() * 20),
  });
}
</script>

<template>
  <VRow>
    <!-- 👉 Apple iPhone 11 Pro -->
    <VCol v-for="metric in metrics" :key="metric.id" sm="2" cols="4">
      <VCard v-if="metric.SpO2 > 95">
        <div
          class="d-flex justify-space-between flex-wrap flex-md-nowrap flex-column flex-md-row" style="background-color: pink;"
        >
          <div>
            <VCardItem>
                <VCardTitle>{{ metric.patient_id }}</VCardTitle>
              
            </VCardItem> 

            <VCardText class="text-subtitle-1" style="font-size: x-small;">
              <span>更新時間 : {{ metric.time }}</span>
            </VCardText>

          </div>

          <VDivider :vertical="$vuetify.display.mdAndUp" />

          <div class="ma-auto">
            <VCardText class="text-subtitle-1">
              <span> SpO2:</span>
              <span style="font-size: large; font-weight: bold; color: red;">{{ metric.SpO2 }}</span>
            </VCardText>
            <VDivider :horizontal="$vuetify.display.mdAndUp" />
            <VCardText class="text-subtitle-1">
              <span>PR:</span>
              <span class="font-weight-large">{{ metric.PR }}</span>
            </VCardText>
          </div>
        </div>
      </VCard>

      <VCard v-if="metric.SpO2 <= 95">
        <div
          class="d-flex justify-space-between flex-wrap flex-md-nowrap flex-column flex-md-row" style="color: red;"
        >
          <div>
            <VCardItem>
              <VCardTitle>{{ metric.patient_id }}</VCardTitle>
            </VCardItem>
            
            <VCardText class="text-subtitle-1">
              <span>更新時間 : {{ metric.time }}</span>
            </VCardText>
          </div>

          <VDivider :vertical="$vuetify.display.mdAndUp" />

          <div class="ma-auto">
            <VCardText class="text-subtitle-1">
              <span> SpO2:</span>
              <span style="font-size: large; font-weight: bold; color: black;">{{ metric.SpO2 }}</span>
            </VCardText>
            <VDivider :horizontal="$vuetify.display.mdAndUp" />
            <VCardText class="text-subtitle-1">
              <span>PR:</span>
              <span class="font-weight-medium">{{ metric.PR }}</span>
            </VCardText>
          </div>
        </div>
      </VCard>
    </VCol>
  </VRow>
</template>

<style lang="scss" scoped>
.avatar-center {
  position: absolute;
  border: 3px solid rgb(var(--v-theme-surface));
  inset-block-start: -2rem;
  inset-inline-start: 1rem;
}

// membership pricing
.member-pricing-bg {
  position: relative;
  background-color: rgba(var(--v-theme-on-surface), var(--v-hover-opacity));
}

.membership-pricing {
  sup {
    inset-block-start: 9px;
  }
}
</style>
