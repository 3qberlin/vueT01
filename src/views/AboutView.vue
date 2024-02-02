<template>
  <div class="about">
    <h1>This is an about page??</h1>
    {{ data }}
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
      data: {}
    }
  },
  mounted() {
    const url = import.meta.env.VITE_PATH;
    const text = import.meta.env.VITE_TEXT;
    const product = import.meta.env.VITE_PROD;
    this.$http.get(url).then((res) => {
      console.log(res)
      console.log('text',text);
      console.log('product',product);
      this.data = res.data.info.seed
    })
  }
}
</script>
