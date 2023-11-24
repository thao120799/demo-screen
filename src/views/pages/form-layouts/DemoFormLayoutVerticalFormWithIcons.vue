<script setup>
const firstName = ref("");
const email = ref("");
const mobile = ref();
const password = ref();
const checkbox = ref(false);
</script>

<template>
  <VForm @submit.prevent>
    <VRow>
      <VCol cols="12" md="6">
        <VTextField
          v-model="firstName"
          prepend-inner-icon="bx-user"
          label="お名前"
          placeholder="山田"
        />
      </VCol>

      <!-- 👉 Last Name -->
      <VCol cols="12" md="6">
        <VTextField
          v-model="lastName"
          prepend-inner-icon="bx-user"
          label="お名前（ふりがな）"
          placeholder="ヤマダ"
        />
      </VCol>

      <VCol cols="1">
        <p style="margin-top: 20px;"> 生年月日 </p>
      </VCol>

      <VCol cols="3">
        <v-select
          label="月"
          :items="[
            'California',
            'Colorado',
            'Florida',
            'Georgia',
            'Texas',
            'Wyoming',
          ]"
        ></v-select>
      </VCol>

      <VCol cols="3">
        <v-select
          label="月"
          :items="[
            'California',
            'Colorado',
            'Florida',
            'Georgia',
            'Texas',
            'Wyoming',
          ]"
        ></v-select>
      </VCol>

      <VCol cols="3">
        <v-select
          label="日"
          :items="[
            'California',
            'Colorado',
            'Florida',
            'Georgia',
            'Texas',
            'Wyoming',
          ]"
        ></v-select>
      </VCol>

      <VCol cols="12">
        <VTextField
          v-model="firstName"
          prepend-inner-icon="bx-home"
          label="住所"
        />
      </VCol>

      <VCol cols="12">
        <VTextField
          v-model="email"
          prepend-inner-icon="bx-envelope"
          label="メール"
          type="email"
          placeholder="yamada@example.com"
        />
      </VCol>

      <VCol cols="12">
        <VTextField
          v-model="mobile"
          prepend-inner-icon="bx-mobile"
          label="電話番号"
          placeholder="+1 123 456 7890"
          type="number"
        />
      </VCol>

      <VCol cols="12" md="12">
        <v-select
          label="保健所"
          :items="['朝日保険', '山田保険', '日進保険']"
        ></v-select>
      </VCol>

      <VCol cols="12" md="12">
        <v-select label="機器情報" :items="['1', '2', '3']"></v-select>
      </VCol>

      <VCol cols="12" md="12">
        <v-select label="重病度" :items="['なし', '軽い', '重い']"></v-select>
      </VCol>

      <VCol cols="12">
        <VBtn type="submit" class="me-2"> 登録 </VBtn>

        <VBtn color="secondary" type="reset" variant="tonal"> キャンセル </VBtn>
      </VCol>
    </VRow>
  </VForm>
</template>
