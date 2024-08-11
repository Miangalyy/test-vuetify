<template>
    <Doughnut :data="CharacterData" :options="chartOptions" />
</template>
<script>
  import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js';
  import { Doughnut } from 'vue-chartjs';

  ChartJS.register(ArcElement, Tooltip, Legend)

  export default {
    data: () => ({
        CharacterData: {
            labels: ['VueJs', 'EmberJs', 'ReactJs', 'AngularJs'],
            datasets: [
                {
                    backgroundColor: ['#418883', '#e46651', '#00d8ff', '#dd1816'],
                    data: [40, 20, 80, 10]
                }
            ]
        },
        chartOptions: {
            responsive: true
        }
    }),
    components: {
        Doughnut,
    },
  }
</script>