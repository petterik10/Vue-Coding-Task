<template>
  <div class="ticket-overview">
    Nur noch {{ showAvailableTickets }} Tickets vorhanden
  </div>
</template>

<script>
export default {
  name: "TicketOverview",
  props: {
    showAvailableTickets: Number,
  },
};
</script>

<style>
.ticket-overview {
  text-align: center;
  margin-top: 35px;
  font-size: 20px;
}
</style>
