<template>
  <!-- Componente do gráfico -->
  <div>
   <!-- o "type" eu defino qual gráfico será abordado
    o "data" ele avincula o valor de chartData ao tributo data(A variável chartData é definida no bloco <script setup>, e ela contém os dados que o gráfico vai exibir)
     "options" é usada para configurar o grafico como :titulo, subtitulo e outras opçoes  -->
    <GChart
    
      type="ColumnChart"  
      :data="chartData"
      :options="chartOptions"
    />
  </div>
</template>

<script setup>
import { GChart } from 'vue-google-charts'; 

// Dados
const chartData = [
  ['Year', 'Sales', 'Expenses', 'Profit'],
  ['2014', 1000, 400, 200],
  ['2015', 1170, 460, 250],
  ['2016', 660, 1120, 300],
  ['2017', 1030, 540, 350],
];

const chartOptions = {
  title: 'Company Performance',
  subtitle: 'Sales, Expenses, and Profit: 2014-2017',
  is3D: true, // Definindo como 3D (opcional)
};

</script>

<style scoped>
/* Adicione estilos se necessário */
</style>
