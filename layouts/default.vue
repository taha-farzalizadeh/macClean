<template>
  <div>
    <sidebar/>
    <div class="main-content">
      <Nuxt />
    </div>
  </div>
</template>

<style>
html {
  font-family:
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}
body{
  font-family: Quicksand;
  background-color: #f8f8fc;
}
.main-content{
  margin: 35px 0px 20px 180px;
}
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}
</style>
