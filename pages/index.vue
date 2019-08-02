<template>
  <div>
    <couponItem v-for="product in products" v-bind:key="product.id" :product="product" />
  </div>
</template>

<script>
import couponItem from '../components/couponItem'

export default {
  components: {
    couponItem
  },
  async asyncData({ $axios }) {
    const data = await $axios.$get(
      'http://5d41acf975f67300146b4228.mockapi.io/Products'
    )

    console.log(data)
    return { products: data }
  }
}
</script>

<style>
</style>
