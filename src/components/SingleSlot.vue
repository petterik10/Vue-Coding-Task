<template>
  <div>
    <div
      class="individual-slot"
    >
      {{ individualSlot.begin }}
    </div>
    <div :class="[slotId === individualSlot.id ? 'selected-slot' : '']">
      {{ individualSlot.price.amount.toFixed(2).toString().replace(".", ",")
      }}<span>€</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "SingleSlot",
  props: {
    individualSlot: Object,
    slotId: String,
  },
};
</script>

<style>
.individual-slot {
  border-bottom: 2px solid #6ed66d;
  text-align: center;
}

.selected-slot {
  border-top: 2px solid white;
  font-size: 20px;
}

span {
  display: inline-block;
  margin-top: 2px;
}
</style>
