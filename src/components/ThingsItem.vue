<script setup>
const props = defineProps({
  item: {
    type: Object,
    required: true
  }
})
</script>

<template>
  <div class="things_item">
    {{ item.name }}
  </div>
</template>

<style>
.things_item {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100px;
  height: 100px;
  border: #000 solid 3px;
  cursor: pointer;
}
</style>