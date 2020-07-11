<template>
  <div class="pill">
    <span class="name">{{ name }}</span>
    <span class="amount">{{ amount }}</span>
  </div>
</template>

<script>
export default {
  props: ["name", "amount"]
};
</script>

<style scoped>
.pill {
  margin: 10px;
  height: 55px;
  border-radius: 30px;
  background: rgba(216, 19, 59, 0.92);
  color: #fff;
  font-size: 1.3rem;
  font-weight: bold;
  display: flex;
  align-items: center;
}

.pill .name {
  margin-left: 15px;
}

.pill .amount {
  margin: 10px;
  padding: 5px;
  height: 35px;
  width: 35px;
  border-radius: 50%;
  background: white;
  color: rgba(216, 19, 59, 0.92);
  font-size: 14px;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>