<template>
  <div>
    <h1>Products</h1>
    <div class="products">
      <div v-for="(product, index) in products" :key="index">
        <h3>{{product.name}}</h3>
        <div class="cost">{{product.cost}}</div>
        <img :src="product.image" />
        <button v-on:click="addItemToCart(product)">Add to cart</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      products: [
        {
          name: "Football",
          cost: "Rs 1500",
          image:
            "https://tse3.mm.bing.net/th?id=OIP.h27C509yHNEUCPzikGx2QQHaJ4&pid=Api&P=0&w=300&h=300"
        },
        {
          name: "Cricket Kit",
          cost: "Rs 2000",
          image:
            "https://tse4.mm.bing.net/th?id=OIP.zCewkhFV8bcHkL6_ChzqqgHaHa&pid=Api&P=0&w=300&h=300"
        },
        {
          name:"Basketball",
          cost:"1700",
          image:
          "https://tse2.mm.bing.net/th?id=OIP.Oo9b-8YJ5KAkxfCj9WaSjgHaJQ&pid=Api&P=0&w=300&h=300"
        }
      ]
    };
  },
  methods: {
    addItemToCart(product) {
      this.$emit("addItemToCart", product);
    }
  }
};
</script>

<style>
</style>