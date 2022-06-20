<template>
  <div>
    <navigation-bar />
    <filters-component :searchInput.sync="searchInput" :filtered="filtered" />
    <results-component :items="items" />
  </div>
</template>

<script>
import NavigationBar from "./../components/navigation-bar.vue";
import FiltersComponent from "./../components/filters-component.vue";
import ResultsComponent from "./../components/results-component.vue";

export default {
  name: "HomePage",
  components: {
    NavigationBar,
    FiltersComponent,
    ResultsComponent,
  },
  data() {
    return {
      searchInput: "",
      filtered: [],
      items: [
        {
          img: "1.jpg",
          name: "Crowne plaza Zurich",
          address: "Hotel - Zurich, Sweiz",
          stars: 5,
          trophy: true,
          distance: 2.9,
          rating: 8.5,
          reviews: 3910,
          price: 970,
        },
        {
          img: "2.jpg",
          name: "Hotel ibis budget Zurich City West",
          address: "Hotel - Zurich, Sweiz",
          stars: 1,
          trophy: false,
          distance: 2.8,
          rating: 7.4,
          reviews: 1395,
          price: 630,
        },
        {
          img: "3.jpg",
          name: "Meininger Zurich-Greencity",
          address: "Hotel - Zurich, Sweiz",
          stars: 0,
          trophy: false,
          distance: 3.8,
          rating: 7.7,
          reviews: 12,
          price: 979,
        },
        {
          img: "4.jpg",
          name: "Crw Zurich-Greencity",
          address: "Hotel - Zurich, Sweiz",
          stars: 0,
          trophy: false,
          distance: 3.8,
          rating: 7.7,
          reviews: 12,
          price: 979,
        },
      ],
    };
  },
  watch: {
    searchInput(val) {
      this.filterItems(val);
    },
  },
  methods: {
    filterItems(val) {
      this.filtered = this.items.filter((i) => {
        if (val !== "") {
          return i.name.toLowerCase().startsWith(val.toLowerCase());
        }
      });
    },
  },
};
</script>
