<script setup>
import VueApexCharts from "vue3-apexcharts";
import { useTheme } from "vuetify";
import statsVerticalChart from "@images/cards/chart-success.png";
import statsVerticalPaypal from "@images/cards/paypal-error.png";
import statsVerticalWallet from "@images/cards/wallet-primary.png";
import { hexToRgb } from "@layouts/utils";

const vuetifyTheme = useTheme();

const series = {
  income: [
  {
            name: 'SP02',
            type: 'line',
            data: [23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30, 23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30,23, 11]
          }, {
            name: 'PR',
            type: 'area',
            data: [44, 55, 41, 67, 22, 43, 21, 41, 56, 27, 43,23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30,23, 11]
          }
  ],
  expenses: [
  {
            name: 'SP02',
            type: 'line',
            data: [13, 22, 20, 27, 13, 45,324,54,234,423,43,23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30,23, 11]
          }, {
            name: 'PR',
            type: 'area',
            data: [44, 55, 41, 67, 22, 43, 21, 41, 56, 27, 43,23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30,23, 11]
          }
  ],
  profit: [
  {
            name: 'SP02',
            type: 'line',
            data: [243, 11, 224, 273, 143, 22,237, 21, 44, 22, 30,23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30,23, 11]
          }, {
            name: 'PR',
            type: 'area',
            data: [44, 55, 41, 67, 22, 43, 21, 41, 56, 27, 43,23, 11, 22, 27, 13, 22, 37, 21, 44, 22, 30,23, 11]
          }
  ],
};

const currentTab = ref("income");

const tabData = computed(() => {
  const data = {
    income: {
      avatar: statsVerticalWallet,
      title: "日",
    },
    expenses: {
      avatar: statsVerticalPaypal,
      title: "週",
    },
    profit: {
      avatar: statsVerticalChart,
      title: "月",
    },
  };

  return data[currentTab.value];
});

const chartOptions = computed(() => {
  const currentTheme = vuetifyTheme.current.value.colors;
  const variableTheme = vuetifyTheme.current.value.variables;
  const disabledTextColor = `rgba(${hexToRgb(
    String(currentTheme["on-surface"])
  )},${variableTheme["disabled-opacity"]})`;
  const borderColor = `rgba(${hexToRgb(
    String(variableTheme["border-color"])
  )},${variableTheme["border-opacity"]})`;

  return {
    chartOptions: {
            chart: {
              height: 350,
              type: 'line',
              stacked: false,
            },
            stroke: {
              width: [0, 2, 5],
              curve: 'smooth'
            },
            plotOptions: {
              bar: {
                columnWidth: '50%'
              }
            },
            
            fill: {
              opacity: [0.85, 0.25, 1],
              gradient: {
                inverseColors: false,
                shade: 'light',
                type: "vertical",
                opacityFrom: 0.85,
                opacityTo: 0.55,
                stops: [0, 100, 100, 100]
              }
            },
            labels: ['01/01/2003', '02/01/2003', '03/01/2003', '04/01/2003', '05/01/2003', '06/01/2003', '07/01/2003',
              '08/01/2003', '09/01/2003', '10/01/2003', '11/01/2003'
            ],
            markers: {
              size: 0
            },
            xaxis: {
              type: 'datetime'
            },
            yaxis: {
              title: {
                text: 'Points',
              },
              min: 0
            },
            tooltip: {
              shared: true,
              intersect: false,
              y: {
                formatter: function (y) {
                  if (typeof y !== "undefined") {
                    return y.toFixed(0) + " points";
                  }
                  return y;
            
                }
              }
            }
          },
  };
});

</script>

<template>
  <VCard>
    <VCardItem>
      <VRow style="margin-top: 25px">
        <VCol>
          <VTabs v-model="currentTab" class="v-tabs-pill">
            <VTab value="income"> 日 </VTab>
            <VTab value="expenses"> 週 </VTab>
            <VTab value="profit"> 月 </VTab>
          </VTabs>
        </VCol>
        <VCol>
          <VSelect
            label="患者"
            :items="[
              '患者１',
              '患者2',
              '患者3',
              '患者4',
            ]"
          ></VSelect>
        </VCol>
      </VRow>
    </VCardItem>

    <VCardText>
      <VueApexCharts
        type="line"
        :height="350"
        :options="chartOptions"
        :series="series[currentTab]"
      />
    </VCardText>
  </VCard>
</template>
