<script setup>
    import { onMounted } from 'vue'
    import Chart from 'chart.js/auto'

    onMounted(() => {
        // component is now mounted.
        // default chartjs line chart with some added datasets for interest
        const labels = ['Jan','Feb','Mar','Apr','May','June','July']
        const data = {
            labels: labels,
            datasets: [
                {
                    label: 'Dataset #1',
                    data: [65, 59, 80, 81, 56, 55, 40],
                    fill: false,
                    borderColor: 'rgb(75, 192, 192)',
                    backgroundColor: 'rgba(75, 192, 192, .2)',
                    tension: 0.1
                },
                {
                    label: 'Dataset #2',
                    data: [2, 43, 12, 75, 87, 31, 60],
                    fill: false,
                    borderColor: 'rgb(54, 162, 235)',
                    backgroundColor: 'rgba(54, 162, 235, .2)',
                    tension: 0.1
                },
                {
                    label: 'Dataset #3',
                    data: [52, 78, 32, 90, 12, 42, 16],
                    fill: false,
                    borderColor: 'rgb(153, 102, 255',
                    backgroundColor: 'rgba(153, 102, 255, .2)',
                    tension: 0.1
                }
            ]
        };
        const config = {
            type: 'line',
            data: data,
            options: {
                plugins: {
                    title: {
                        display: true,
                        text: 'Line Chart Example'
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
        const lineChart = document.getElementById('linechart')
        new Chart(
            lineChart,
            config
        );
    })
</script>

<template>
    <canvas id="linechart" width="350" height="350" aria-label="This is a sample line chart showing data from January to July" role="img" tabindex="0"></canvas>
</template>

<style scoped>
</style>
