<template>
  <div class="about">
    <h1>This Is An About Page</h1>
    {{ data }}
    <p></p>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>

<script>
export default {
data() {
  return {
    data:{},
  }
},
mounted() {
// console.log(import.meta.env.VITE_TEXT);
const url = import.meta.env.VITE_PATH;
this.$http.get(url)
.then((res) => {
  this.data = res.data.results[0];
})
},
}
</script>