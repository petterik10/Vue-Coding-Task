<template>
  <div
    @click="$emit('set-slot', individualSlot.id)"
    class="single-slot"
    :key="individualSlot.id"
    v-for="individualSlot in timeSlots"
    :class="[currentSlot === individualSlot.id ? 'selected-slot' : '']"
  >
    <SingleSlot :slotId="currentSlot" :individualSlot="individualSlot" />
  </div>
</template>

<script>
import SingleSlot from "./SingleSlot";
export default {
  name: "TimeSlots",
  props: {
    timeSlots: Array,
    currentSlot: String,
  },
  components: {
    SingleSlot,
  },
  emits: ["set-slot"],
};
</script>

<style>
.single-slot {
  padding: 10px 10px;
  border: 2px solid #6ED66D;
  border-radius: 10px;
  color: #6ED66D;
  font-size: 20px;
}

.selected-slot {
  background-color: #6ED66D;
  color: white;
}
</style>
