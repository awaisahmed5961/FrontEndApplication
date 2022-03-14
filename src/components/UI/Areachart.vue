<template>
  <apexchart type="area" height="300" :options="chartOptions" :series="series"></apexchart>
</template>

<script>
export default {
  name: "Areachart",
  props: ["categories", "values", "lablel"],
  data: function () {
    return {
      series: [
        {
          name: this.lablel[0],
          data: this.values[0],
        },
        {
          name: this.lablel[1],
          data: this.values[1],
        },
      ],
      chartOptions: {
        chart: {
          type: "area",
        },
        toolbar: {
          show: false,
          tools: {
            download: false,
            selection: false,
            zoom: false,
            zoomin: false,
            zoomout: false,
            pan: false,
            reset: false,
            customIcons: [],
          },
        },
        dataLabels: {
          enabled: false,
        },
        zoom: {
          enabled: false,
        },
        stroke: {
          curve: "smooth",
        },
        xaxis: {
          type: "date",
          categories: this.categories,
        },
        tooltip: {
          // x: {
          //   format: "dd/MM/yy HH:mm",
          // },
        },
        grid: {
          show: false,
          borderColor: "#4E5677",
        },
      },
    };
  },
};
</script>

