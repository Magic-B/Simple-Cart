<script setup>
import ThingsItem from './ThingsItem.vue'
import { useThingsStore } from '../stores/ThingsStore'
import { storeToRefs } from 'pinia'

const thingsStore = useThingsStore()
const { userThingsCart } = storeToRefs(thingsStore)
</script>

<template>
  <div class="things_cart">
    <ThingsItem
      v-for="item in userThingsCart"
      :key="item.id"
      :item="item"
      @click="thingsStore.removeFromUserCart(item)"
    />
    <div class="selected_info">selected: {{userThingsCart.length || 'N/M'}}</div>
  </div>
</template>

<style scoped>
.things_cart {
  position: relative;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(100px, 1fr));
  grid-template-rows: auto 1fr;
  justify-content: space-around;
  gap: 10px;
  padding: 10px;
  width: 350px;
  min-height: 300px;
  border: #000 solid 5px;
}
.selected_info {
  position: absolute;
  margin: 0 auto;
  left: 0;
  right: 0;
  bottom: 0;
  text-align: center;
}
</style>
