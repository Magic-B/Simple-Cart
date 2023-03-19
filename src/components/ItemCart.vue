<script setup>
import { storeToRefs } from 'pinia'
import { useThingsStore } from '../stores/ThingsStore'

const thingsStore = useThingsStore()
const { selected } = storeToRefs(thingsStore)
</script>

<template>
  <div class="item_cart">
    {{ selected?.name }}
  </div>
</template>

<style>
.item_cart {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 200px;
  height: 200px;
  font-size: 22px;
  border: #000 solid 5px;
}
</style>