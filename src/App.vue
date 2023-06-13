<template>
  <div class="app">
    <div class="nav-app-container">
      <div class="nav-app">
        <div class="img-logo">
          <p>My balance</p>

          <img class="logo" src="@/assets/logo.svg" alt="logo" />
        </div>
        <p>$ 921.48</p>
      </div>
      <div class="header">
        <h2>Spending - Last 7 days</h2>

        <p>mon</p>
        <p>tue</p>
        <p>wed</p>
        <p>thu</p>
        <p>fri</p>
        <p>sat</p>
        <p>sun</p>
      </div>
    </div>
  </div>
</template>
<style>
body {
  margin: 0;
}
.app {
  background-color: #ffeee0;
  justify-content: center;
  display: flex;
  padding-top: 10%;
  height: 100vh;
}
.nav-app-container {
  width: 40%;
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
}
.header {
  background-color: rgba(255, 255, 255, 0.83);
  color: rgb(53, 53, 53);
  border-radius: 10px;
  padding: 20px;
  margin-top: 20px;
  display: block;
}
</style>