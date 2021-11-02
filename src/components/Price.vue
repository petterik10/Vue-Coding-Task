<template>
  <div class="price">
    {{ priceCount.toFixed(2).toString().replace(".", ",") }}€
  </div>
</template>

<script>
export default {
  name: "Price",
  props: {
    priceCount: Number,
  },
};
</script>

<style>
.price {
  text-align: center;
  color: #6ed66d;
  margin-top: 20px;
  font-size: 25px;
  font-weight: bold;
}
</style>
