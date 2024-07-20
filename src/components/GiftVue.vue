<template>
  <div class="gift">
    <div class="gift-tie-1"/>
    <div class="gift-tie-2"/>
    <div class="gift-top"/>
    <div class="gift-body"/>
  </div>
</template>

<script>
export default {
  name: 'GiftVue',
}
</script>

<style>
.gift {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  z-index: 10;
}

.gift-top {
  width: 100px;
  height: 25px;
  background-color: rgba(163, 55, 55, 0.842);
}

.gift-body {
  width: 90px;
  height: 60px;
  background-color: rgb(170, 63, 63);
}

.gift-tie-1 {
  position: absolute;
  width: 15px;
  height: 85px;
  background-color: chocolate;
}

.gift-tie-2 {
  position: absolute;
  top: 40px;
  width: 90px;
  height: 15px;
  background-color: chocolate;
}
</style>