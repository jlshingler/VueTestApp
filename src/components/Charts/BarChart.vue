<script setup>
    import { onMounted } from 'vue'
    import Chart from 'chart.js/auto'

    onMounted(() => {
        // component is now mounted.
        // this is the chartjs default barchart for now
        const labels = ['Jan','Feb','Mar','Apr','May','June','July']
        const data = {
            labels: labels,
            datasets: [{
                label: 'Data Set #1',
                data: [65, 59, 80, 81, 56, 55, 40],
                backgroundColor: [
                    'rgba(255, 99, 132, 0.2)',
                    'rgba(255, 159, 64, 0.2)',
                    'rgba(255, 205, 86, 0.2)',
                    'rgba(75, 192, 192, 0.2)',
                    'rgba(54, 162, 235, 0.2)',
                    'rgba(153, 102, 255, 0.2)',
                    'rgba(201, 203, 207, 0.2)'
                ],
                borderColor: [
                    'rgb(255, 99, 132)',
                    'rgb(255, 159, 64)',
                    'rgb(255, 205, 86)',
                    'rgb(75, 192, 192)',
                    'rgb(54, 162, 235)',
                    'rgb(153, 102, 255)',
                    'rgb(201, 203, 207)'
                ],
                borderWidth: 1
            }]
        }
        const config = {
            type: 'bar',
            data: data,
            options: {
                plugins: {
                    title: {
                        display: true,
                        text: 'Bar Chart Example'
                    },
                    legend: {
                        position: 'bottom'
                    }
                },
                scales: {
                    y: {
                        beginAtZero: true
                    }
                },
                responsive: false
            },
        }
        const barChart = document.getElementById('barchart')
        new Chart(
            barChart,
            config
        );
    })
</script>

<template>
    <canvas id="barchart" width="350" height="350" aria-label="This is a sample bar chart showing data from January to July" role="img" tabindex="0"></canvas>
</template>

<style scoped>

</style>
