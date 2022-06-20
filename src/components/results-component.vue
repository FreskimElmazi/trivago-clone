<template>
  <div>
    <card-component v-for="(item, i) in items" :key="i" :item="item" />
  </div>
</template>

<script>
import CardComponent from "./card-component.vue";
export default {
  name: "ResultsComponent",
  components: {
    CardComponent,
  },
  props: {
    items: {
      type: Array,
      default: function () {
        return [];
      },
    },
  },
};
</script>
