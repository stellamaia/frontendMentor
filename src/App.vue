<template>
  <div class="app">
    <div class="nav-app-container">
      <div class="nav-app">
        <div class="img-logo">
          <p class="title-balance">My balance</p>

          <img class="logo" src="@/assets/logo.svg" alt="logo" />
        </div>
        <p class="money-nav">$ 921.48</p>
      </div>
      <div class="header">
        <h2 class="title-header">Spending - Last 7 days</h2>
        <canvas class="myChart" id="myChart"></canvas>
        <v-divider class="divider"></v-divider>
        <p class="title-month">Total this month</p>
        <div class="content-header">
          <h1 class="money">$478.33</h1>
          <div class="content-infos">
            <p class="money-percentage">+2.4%</p>
            <p class="money-month">from last month</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import jsonData from "/data.json";
import Chart from "chart.js";
export default {
  name: "App",
  data() {
    return {
      data: jsonData,
      chart: null,
    };
  },
  mounted() {
    this.renderChart();
  },
  methods: {
    renderChart() {
      const ctx = document.getElementById("myChart");

      this.chart = new Chart(ctx, {
        type: "bar",
        data: {
          labels: this.data.map((item) => item.day),
          datasets: [
            {
              label: "Amount",
              data: this.data.map((item) => item.amount),
              backgroundColor: "rgba(245, 80, 80, 0.83)",
              borderColor: "transparent",
              borderWidth: 1,

              hoverBackgroundColor: "rgba(80, 174, 245, 0.83)", // Corrigido: removido o ponto e vírgula
            },
          ],
        },
        options: {
          legend: {
            display: false, // Remove a exibição do rótulo do conjunto de dados
          },
          scales: {
            xAxes: [
              {
                gridLines: {
                  display: false,
                },
                ticks: {
                  fontColor: "gray", // Cor do texto
                  fontWeight: "bold", // Peso da fonte
                },
              },
            ],
            yAxes: [
              {
                gridLines: {
                  display: false,
                },
                ticks: {
                  display: false, // Remove os ticks do eixo Y
                },
              },
            ],
          },
        },
      });
    },
  },
};
</script>

<style>
body {
  margin: 0;
}

.app{
  background-color: #ffeee0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
.title-balance {
  font-size: 13px;
}
.money-nav {
  font-weight: 600;
}

.nav-app {
  background-color: rgb(245 80 80 / 83%);
  color: white;
  border-radius: 10px;
  padding: 20px;

}
.nav-app,
.header {
  font-family: Arial, Helvetica, sans-serif;
}
.valor {
  display: block;
}

.img-logo {
  display: flex;
  justify-content: space-between;
  height: 30px;
}
.header {
  background-color: rgba(255, 255, 255, 0.83);
  color: rgb(75, 56, 56);
  border-radius: 10px;
  padding: 20px;
  margin-top: 20px;
  display: block;
box-shadow: 1px 15px 20px 8px rgba(0, 0, 0, 0.2);
}
.title-header {
  font-size: 20px;
  font-weight: 600;
  text-align: center;
  color: rgb(75, 56, 56);
  padding: 10px;
}
.myChart {
  cursor: pointer;
}
.divider {
  background-color: red;
}
.title-month {
  color: rgba(75, 56, 56, 0.461);
  margin: 0;
  font-size: 13px;
  padding: 0 10px 0 10px;
}
.money {
  font-weight: 600;
  padding: 0;
  color: rgb(75, 56, 56);
}
.money-percentage {
  margin: 5px 0 0 0;
  font-weight: 600;
  font-size: 11px;
  justify-content: end;
  display: flex;
}
.money-month {
  color: rgba(75, 56, 56, 0.461);
  font-size: 13px;
}
.content-header {
  justify-content: space-between;
  display: flex;
  padding: 0 10px 0 10px;
}
@media screen and (max-width: 480px) {

  .header {
    padding: 0;
  }
 
}


</style>