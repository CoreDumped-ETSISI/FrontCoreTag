<template>
    <div class="row">
        <div class="col s9">
            <div class="card">
                <!-- Custom information -->
                <div class="about">
                    <h3>Carlos🦄</h3>
                    <p class="lead">Shooting Statistics By Minute</p>
                    <div class="legends">
                        <div class="info">
                            <span class="legend legend--this"></span>
                            <p>Shoots</p>
                        </div>
                        <div class="info">
                            <span class="legend legend--prev"></span>
                            <p>Deaths</p>
                        </div>
                    </div>
                </div>

                <!-- Canvas for Chart.js -->
                <canvas id="canvas"></canvas>

                <!-- Custom Axis -->
                <div class="axis">
                    <div class="tick">
                        1"
                        <span class="value value--this">24</span>
                        <span class="value value--prev">20</span>
                    </div>
                    <div class="tick">
                        2"
                        <span class="value value--this">18</span>
                        <span class="value value--prev">22</span>
                    </div>
                    <div class="tick">
                        3"
                        <span class="value value--this">16</span>
                        <span class="value value--prev">30</span>
                    </div>
                    <div class="tick">
                        4"
                        <span class="value value--this">18</span>
                        <span class="value value--prev">22</span>
                    </div>
                    <div class="tick">
                        5"
                        <span class="value value--this">24</span>
                        <span class="value value--prev">18</span>
                    </div>
                    <div class="tick">
                        6"
                        <span class="value value--this">36</span>
                        <span class="value value--prev">22</span>
                    </div>
                    <div class="tick">
                        7"
                        <span class="value value--this">28</span>
                        <span class="value value--prev">30</span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Chart',
    created: function(){
        $(document).ready(function(){
            var canvas = document.getElementById("canvas");

            // Apply multiply blend when drawing datasets
            var multiply = {
                beforeDatasetsDraw: function(chart, options, el) {
                    chart.ctx.globalCompositeOperation = 'multiply';
                },
                afterDatasetsDraw: function(chart, options) {
                    chart.ctx.globalCompositeOperation = 'source-over';
                },
            };

            // Gradient color - this week
            var gradientThisWeek = canvas.getContext('2d').createLinearGradient(0, 0, 0, 150);
            gradientThisWeek.addColorStop(0, '#5555FF');
            gradientThisWeek.addColorStop(1, '#9787FF');

            // Gradient color - previous week
            var gradientPrevWeek = canvas.getContext('2d').createLinearGradient(0, 0, 0, 150);
            gradientPrevWeek.addColorStop(0, '#FF55B8');
            gradientPrevWeek.addColorStop(1, '#FF8787');


            var config = {
                type: 'line',
                data: {
                    labels: ["1", "2", "3", "4", "5", "6", "7"],
                    datasets: [
                        {
                            label: 'This week',
                            data: [24, 18, 16, 18, 24, 36, 28],
                            backgroundColor: gradientThisWeek,
                            borderColor: 'transparent',
                            pointBackgroundColor: '#FFFFFF',
                            pointBorderColor: '#FFFFFF',
                            lineTension: 0.40,
                        },
                        {
                            label: 'Previous week',
                            data: [20, 22, 30, 22, 18, 22, 30],
                            backgroundColor: gradientPrevWeek,
                            borderColor: 'transparent',
                            pointBackgroundColor: '#FFFFFF',
                            pointBorderColor: '#FFFFFF',
                            lineTension: 0.40,
                        }
                    ]
                },
                options: {
                    elements: { 
                        point: {
                            radius: 0,
                            hitRadius: 5, 
                            hoverRadius: 5 
                        } 
                    },
                    legend: {
                        display: false,
                    },
                    scales: {
                        xAxes: [{
                            display: false,
                        }],
                        yAxes: [{
                            display: false,
                            ticks: {
                                beginAtZero: true,
                            },
                        }]
                    }
                },
                plugins: [multiply],
            };

            window.chart = new Chart(canvas, config);
        });
    }
}

</script>

<style>
body {
    background-color: #f3f5f7;
    font-family: 'Helvetica Neue', Arial, sans-serif;
}

.card {
    background-color: #fff;
    box-shadow: 0 0 6px rgba(0, 0, 0, 0.1);
    position: absolute;
    bottom: -30%;
    left: 50%;
    transform: translate(-50%, -50%);
    max-width: 300px;
    height: 375px;
    border-radius: 10px;
    overflow: hidden;
}

.card .about {
    height: 225px;
    padding: 20px;
    box-sizing: border-box;
}

.card .about h3,
.card .about .lead {
    font-weight: 300;
    margin: 0;
}

.card .about h3 {
    font-size: 24px;
}

.card .about .lead {
    color: #aaa;
}

.card .info {
    float: left;
    padding: 10px 30px 10px 0;
}

.card .info p {
    font-size: 11px;
    color: #aaa;
    font-weight: 300;
}

.legends {
    padding-top: 20px;
    overflow: hidden;
}

.legend {
    display: block;
    width: 8px;
    height: 8px;
    margin-top: 15px;
    margin-bottom: 15px;
    border-radius: 50%;
}

.legend--this {
    background-color: #5555FF;
}

.legend--prev {
    background-color: #FF55B8;
}

.axis {
    position: absolute;
    color: #fff;
    z-index: 1;
    text-transform: uppercase;
    display: flex;
    width: 100%;
    bottom: 0;
}

.axis .tick {
    flex: 1;
    position: relative;
    overflow: hidden;
    opacity: 0.2;
    font-size: 11px;
    text-align: center;
    line-height: 40px;
    padding-top: 150px;
}

.axis .tick:hover {
    opacity: 1;
    background-color: rgba(255, 255, 255, 0.2);
}

.axis .tick .value {
    transform: translateY(-40px);
    transition: 0.3s transform;
    position: absolute;
    top: 20px;
    color: #444;
    border-radius: 2px;
    width: 100%;
    line-height: 20px;
}

.axis .tick:hover .value.value--this {
    transform: translateY(0);
    display: block;
}

.value.value--this {
    color: #5555FF;
    font-weight: bold;
}
</style>
