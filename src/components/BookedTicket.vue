<template>
  <div @click="$emit('bookTicket')" class="booking-button">Jetzt Buchen</div>
</template>

<script>
export default {
  name: "BookedTicket",
};
</script>

<style>
.booking-button {
  background-color: #FA9237;
  border: none;
  color: white;
  text-align: center;
  text-decoration: none;
  font-size: 16px;
  padding: 15px;
  border-radius: 10px;
  display: grid;
  left: 15px;
  right: 15px;
  position: absolute;
  bottom: 20px;
  font-size: 20px;
}
</style>
