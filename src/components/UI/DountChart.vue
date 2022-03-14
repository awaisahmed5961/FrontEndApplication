<template>
  <div class="chart-area">
    <apexchart type="donut" height="440" :options="chartOptions" :series="series"></apexchart>
  </div>
</template>

<script>
export default {
  name: "Areachart",
  props: ["seriess", "lables", "colors"],
  data() {
    return {
      series: this.seriess,
      chartOptions: {
        labels: this.lables,
        chart: {
          width: "100%",
          type: "donut",
        },
        dataLabels: {
          enabled: false,
        },
        fill: {
          colors: this.colors,
        },
        colors: this.colors,
        plotOptions: {
          pie: {
            donut: {
              size: "80%",
              donut: {
                labels: {
                  show: true,
                  name: {
                    show: true,
                  },
                  value: {
                    show: true,
                  },
                },
              },
            },
          },
        },
        responsive: [
          {
            breakpoint: 480,
            options: {
              chart: {
                width: 200,
              },
              legend: {
                show: false,
              },
            },
          },
        ],
        legend: {
          position: "bottom",
          offsetY: 0,
          height: 230,
        },
      },
    };
  },
};
</script>

