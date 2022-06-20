<template>
  <button :class="['btn', buttonClass, size]"><slot></slot></button>
</template>

<script>
export default {
  name: "ButtonComponent",
  props: {
    buttonClass: {
      type: String,
      required: false,
    },
    size: {
      type: String,
      required: false,
    },
  },
};
</script>

<style scoped>
button.btn {
  height: 2.75rem;
  background-color: silver;
  color: black;
  border: none;
  border-radius: 0.5rem;
  padding-left: 20px;
  padding-right: 20px;
}

button.btn:hover {
  cursor: pointer;
}

.btn.primary {
  background-color: #4285f4;
  color: white;
}

.btn.primary:hover {
  background-color: #0161fa;
}

.btn.success {
  background-color: #00c851;
  color: white;
}

.btn.success:hover {
  background-color: #019c3f;
}

.btn.danger {
  background-color: #ff4444;
  color: white;
}

.btn.danger:hover {
  background-color: #e62b2b;
}

.btn.small {
  height: 35px;
}
</style>
