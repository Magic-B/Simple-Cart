<script setup>
import ThingsItem from './ThingsItem.vue'

defineEmits(['select'])

const props = defineProps({
  itemsData: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <div class="things_storage">
    <ThingsItem
      v-for="item in itemsData"
      :key="item.id"
      :item="item"
      @click="$emit('select', item)"
    />
  </div>
</template>

<style>
.things_storage {
  border: #000 solid 5px;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  grid-template-rows: auto 1fr;
  justify-content: space-around;
  gap: 10px;
  padding: 10px;
  width: 100%;
  min-height: 500px;
}
</style>
