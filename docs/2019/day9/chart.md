# 차트 라이브러리 모듈화

### chart 라이브러리

- chart.js https://www.chartjs.org/
- am chart https://www.amcharts.com/
- high chart https://www.highcharts.com/
- D3 chart https://d3js.org/
- billboard.js https://naver.github.io/billboard.js/

### chart 적용하기

- chart 플러그인 설치: ChartPlugin.js

```js
import Chart from "chart.js";

export default {
  install(Vue) {
    Vue.prototype.$_Chart = Chart;
  },
};
```

- main.js

```js
import Vue from "vue";
import App from "./App.vue";
import ChartPlugin from "./plugins/ChartPlugin.js";

Vue.use(ChartPlugin);

Vue.config.productionTip = false;

new Vue({
  render: h => h(App),
}).$mount("#app");
```

- App.vue

```js
<template>
  <div>
    <!-- TODO: BarChart, LineChart 제작 -->
    <bar-chart></bar-chart>
    <line-chart></line-chart>
  </div>
</template>

<script>
import BarChart from './components/BarChart.vue';
import LineChart from './components/LineChart.vue';
export default {
	components: {
		BarChart,
		LineChart,
	},
	created() {
		console.log(this);
	},
};
</script>
```

- /components/BarChart.vue

```js
<template>
  <canvas
		ref="myChart"
		id="myChart" width="400" height="400"></canvas>
</template>

<script>
export default {
	methods: {
		renderChart() {
			var ctx = this.$refs.myChart.getContext('2d');
			var myChart = new this.$_Chart(ctx, {
				type: 'bar',
				data: {
					labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
					datasets: [
						{
							label: '# of Votes',
							data: [12, 19, 3, 5, 2, 3],
							backgroundColor: [
								'rgba(255, 99, 132, 0.2)',
								'rgba(54, 162, 235, 0.2)',
								'rgba(255, 206, 86, 0.2)',
								'rgba(75, 192, 192, 0.2)',
								'rgba(153, 102, 255, 0.2)',
								'rgba(255, 159, 64, 0.2)',
							],
							borderColor: [
								'rgba(255, 99, 132, 1)',
								'rgba(54, 162, 235, 1)',
								'rgba(255, 206, 86, 1)',
								'rgba(75, 192, 192, 1)',
								'rgba(153, 102, 255, 1)',
								'rgba(255, 159, 64, 1)',
							],
							borderWidth: 1,
						},
					],
				},
				options: {
					scales: {
						yAxes: [
							{
								ticks: {
									beginAtZero: true,
								},
							},
						],
					},
				},
			});
		},
	},
	mounted() {
		this.renderChart();
	},
};
</script>
```

- /components/LineChart.vue

```js
<template>
  <canvas ref="myChart" id="myChart"></canvas>
</template>

<script>
import Chart from 'chart.js';
export default {
	methods: {
		renderChart() {
			var ctx = this.$refs.myChart.getContext('2d');
			// var ctx = document.getElementById('myChart').getContext('2d');
			var chart = new Chart(ctx, {
				// The type of chart we want to create
				type: 'line',
				// The data for our dataset
				data: {
					labels: [
						'January',
						'February',
						'March',
						'April',
						'May',
						'June',
						'July',
					],
					datasets: [
						{
							label: 'My First dataset',
							backgroundColor: 'rgb(255, 99, 132)',
							borderColor: 'rgb(255, 99, 132)',
							data: [0, 10, 5, 2, 20, 30, 45],
						},
					],
				},
				// Configuration options go here
				options: {},
			});
		},
	},
	mounted() {
		this.renderChart();
	},
};
</script>
```
