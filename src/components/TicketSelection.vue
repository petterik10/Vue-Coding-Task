<template>
  <div class="selection-wrapper">
    <div @click="$emit('decreaseCount')" class="decrease-button">
      <span>&#8722;</span>
    </div>
    <div class="ticket-count">{{ ticketCount }} {{ ticketString }}</div>
    <div @click="$emit('increaseCount')" class="increase-button">+</div>
  </div>
</template>

<script>
export default {
  name: "TicketSelection",
  props: {
    ticketCount: Number,
  },
  computed: {
    ticketString() {
      if (this.ticketCount > 1 || this.ticketCount === 0) {
        return "Tickets";
      } else {
        return "Ticket";
      }
    },
  },
};
</script>

<style>
.selection-wrapper {
  display: flex;
  width: 80%;
  margin: auto;
  margin-top: 20px;
  justify-content: space-between;
}

.decrease-button {
  display: inline-block;
  padding: 5px 20px;
  text-align: center;
  border: 2px solid green;
  border-radius: 20px;
  font-weight: bold;
  font-size: 25px;
  cursor: pointer;
}

.increase-button {
  display: inline-block;
  padding: 5px 20px;
  text-align: center;
  border: 2px solid green;
  border-radius: 20px;
  font-weight: bold;
  font-size: 25px;
  cursor: pointer;
}

.ticket-count {
  font-size: 25px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
