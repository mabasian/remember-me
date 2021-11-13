<template>
  <button :class="mode">
    <slot></slot>
  </button>
</template>

<script>
export default {
  props: ['mode'],
};
</script>

<style scoped>
button {
  width: 80px;
  height: 30px;
  font-size: 0.8em;
  background: none;
  border: none;
  color: #148110;
  position: relative;
  cursor: pointer;
}
button::before,
button::after {
  content: '';
  position: absolute;
  top: 0;
  left: -5%;
  width: 100%;
  height: 100%;
  background: #00000000;
  backdrop-filter: blur(70px);
  border-radius: 10px;
  z-index: -2;
}
button::after {
  width: 110%;
  height: 90%;
  top: 25%;
  left: -5%;
  background: #148110;
  z-index: -3;
  transform: scaleX(0.5);
  transition: all 0.6s;
}
button:hover::after {
  transform: scaleX(1.01) translateY(-15px);
}
</style>
