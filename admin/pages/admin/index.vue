<template>
  <section class="grid">
    <order-article></order-article>
    <delivery-not-active></delivery-not-active>
    <orders-main-info></orders-main-info>
    <article><Bar :data="chartData" :options="chartOptions" />
    </article>
    <article></article>
    <article></article>
    <article></article>
    <article></article>
  </section>
</template>
<style src="~/assets/styles/new.css" scoped>
</style>

<script>
import OrderArticle from '~/components/AdminComp/OrderArticle.vue'
import DeliveryNotActive from '~/components/AdminComp/DeliveryNotActive.vue'
import OrdersMainInfo from '../../components/AdminComp/OrdersMainInfo.vue'
export default {
  components: { OrderArticle, DeliveryNotActive, OrdersMainInfo,},

}
</script>
<script setup>
import { Bar } from 'vue-chartjs';
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from 'chart.js';
import { ref } from 'vue';
ChartJS.register(
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

const chartData = ref({
  labels: ['January', 'February', 'March', 'April', 'May'],
  datasets: [
    {
      label: 'Data One',
      backgroundColor: '#f87979',
      data: [40, 20, 12, 50, 10],
    },
  ],
});
const chartOptions = ref({
  responsive: true,
  maintainAspectRatio: false,
});
</script>