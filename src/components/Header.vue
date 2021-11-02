<template>
  <div class="header">
    <img :src="require(`@/assets/dynamaze_logo.png`)" />
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style>
.header {
 text-align: center;
 padding: 5px 0;
}
</style>
