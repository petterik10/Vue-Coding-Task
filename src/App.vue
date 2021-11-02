<template>
  <Header />
  <Image />
  <div class="slot-wrapper">
    <TimeSlots
      @set-slot="setCurrentSlot"
      :currentSlot="currentSlot"
      :timeSlots="timeSlots"
    />
  </div>
  <TicketOverview :showAvailableTickets="showAvailableTickets" />
  <TicketSelection
    @decreaseCount="decreaseCount"
    @increaseCount="increaseCount"
    :ticketCount="ticketCount"
  />
  <Price :priceCount="priceCount" />
  <BookedTicket @bookTicket="bookTicket" />
</template>

<script>
import Header from "./components/Header.vue";
import Image from "./components/Image.vue";
import TimeSlots from "./components/TimeSlots.vue";
import TicketOverview from "./components/TicketOverview.vue";
import Price from "./components/Price.vue";
import BookedTicket from "./components/BookedTicket.vue";
import TicketSelection from "./components/TicketSelection.vue";

export default {
  name: "App",
  components: {
    Header,
    Image,
    TimeSlots,
    TicketOverview,
    Price,
    BookedTicket,
    TicketSelection,
  },
  data: function () {
    return {
      timeSlots: [
        {
          id: "1",
          ticketAmount: 10,
          begin: "10:00",
          price: {
            amount: 10,
            currency: "EUR",
          },
        },
        {
          id: "2",
          ticketAmount: 5,
          begin: "11:00",
          price: {
            amount: 10,
            currency: "EUR",
          },
        },
      ],
      currentSlot: "1",
      ticketCount: 2,
    };
  },
  methods: {
    findCurrentValue(arr, value) {
      let finalValue;
      arr.forEach((elem) => {
        if (this.currentSlot === elem.id) {
          finalValue = elem[value];
        }
      });
      return finalValue;
    },
    filterCurrentSlot() {
      const slot = this.timeSlots.filter((elem) => {
        if (elem.id === this.currentSlot) {
          return elem;
        }
      });
      return slot;
    },
    showTicketString() {
      if (this.ticketCount > 1) {
        return "tickets";
      } else {
        return "ticket";
      }
    },
    setCurrentSlot(id) {
      this.currentSlot = id;
    },
    decreaseCount() {
      if (this.ticketCount === 0) return;
      this.ticketCount--;
    },
    increaseCount() {
      const availableTickets = this.findCurrentValue(
        this.timeSlots,
        "ticketAmount"
      );
      if (availableTickets === this.ticketCount) {
        return;
      }
      this.ticketCount++;
    },
    bookTicket() {
      const timeSlot = this.findCurrentValue(this.timeSlots, "begin");
      const ticketAmount = this.showTicketString();

      alert(
        `Booking TimeSlot at ${timeSlot}, ${
          this.ticketCount
        } ${ticketAmount} at ${this.priceCount
          .toFixed(2)
          .toString()
          .replace(".", ",")}€ succeeded`
      );
    },
  },
  computed: {
    showAvailableTickets() {
      const currentSlot = this.filterCurrentSlot();
      let ticketsAvailable = "";
      currentSlot.forEach((elem) => {
        ticketsAvailable = elem.ticketAmount;
      });
      return ticketsAvailable - this.ticketCount;
    },
    priceCount() {
      const currentSlot = this.filterCurrentSlot();
      let price;
      currentSlot.forEach((elem) => {
        price = elem.price.amount * this.ticketCount;
      });
      return price;
    },
  },
  watch: {
    currentSlot(newValue, oldValue) {
      let previOus;
      let newOne;
      this.timeSlots.forEach((elem) => {
        if (oldValue === elem.id) previOus = elem.ticketAmount;
        if (newValue === elem.id) newOne = elem.ticketAmount;
      });
      if (newOne < previOus) {
        this.ticketCount = 1;
      }
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

.slot-wrapper {
  display: flex;
  justify-content: space-between;
  width: 80%;
  margin: auto;
  margin-top: 20px;
}
</style>
