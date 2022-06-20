<template>
  <div class="filters">
    <div class="input-search">
      <div class="dropdown-content">
        <input
          type="text"
          placeholder="Hotelnamen"
          id="myInput"
          v-model="searchInput"
          @keyup="$emit('update:searchInput', searchInput)"
        />
        <ul v-show="filtered.length">
          <li v-for="(item, i) in filtered" :key="i">
            <div class="search-result">
              <font-awesome-icon
                icon="fa-solid fa-hotel"
                class="search-result-icon"
              />
              {{ item.name }}
              <div class="search-result-address">
                <small>{{ item.address }}</small>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
    <div class="datepicker">
      <div class="datepicker-from">
        <div class="datepicker-icon">
          <font-awesome-icon icon="fa-solid fa-calendar-day" class="icon" />
        </div>
        <div class="datepicker-info">
          <div>Anreise</div>
          <div><b>Do, 23.06.22</b></div>
        </div>
        <div class="datepicker-icon-arrows">
          <font-awesome-icon
            icon="fa-solid fa-angle-left"
            class="icon icon-left"
          />
          <font-awesome-icon
            icon="fa-solid fa-angle-right"
            class="icon icon-right"
          />
        </div>
      </div>
      <div class="datepicker-divider"></div>
      <div class="datepicker-to">
        <div class="datepicker-info">
          <div>Abreise</div>
          <div><b>Fr, 24.06.22</b></div>
        </div>
        <div class="datepicker-icon-arrows">
          <font-awesome-icon
            icon="fa-solid fa-angle-left"
            class="icon icon-left icon-disabled"
          />
          <font-awesome-icon
            icon="fa-solid fa-angle-right"
            class="icon icon-right"
          />
        </div>
      </div>
    </div>
    <div class="persons">
      <div class="persons-icon">
        <font-awesome-icon icon="fa-solid fa-users" class="icon" />
      </div>
      <div class="persons-info">
        <div>5 Zimmer</div>
        <div><b>10 Gaste</b></div>
      </div>
    </div>
    <div class="search-button">
      <button-component buttonClass="primary"
        ><strong>Suchen</strong></button-component
      >
    </div>
  </div>
</template>

<script>
import ButtonComponent from "./button-component.vue";

export default {
  name: "FiltersComponent",
  components: {
    ButtonComponent,
  },
  props: {
    filtered: {
      type: Array,
      default: function () {
        return [];
      },
    },
  },
  data() {
    return {
      searchInput: "",
    };
  },
  methods: {
    getInput() {
      this.$emit();
    },
  },
};
</script>

<style scoped>
#myInput {
  box-sizing: border-box;
  background-image: url("./../assets/icons/search-interface-symbol.png");
  background-position: 14px 12px;
  background-repeat: no-repeat;
  font-size: 16px;
  padding: 14px 20px 12px 45px;
  border: none;
  width: 26rem;
  height: 2.75rem;
  border-radius: 0.5rem;
}

#myInput:focus {
  outline: none;
}

.dropdown-content {
  display: block;
  position: absolute;
  background-color: #fff;
  z-index: 1;
  border-radius: 0.5rem;
}

.dropdown-content ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  box-shadow: 0 1px 10px 0 rgb(10 17 33 / 65%);
  border-radius: .75rem;
}

.dropdown-content ul li {
  text-align: left;
}

.dropdown-content li:hover {
  cursor: pointer;
  background-color: rgba(192, 192, 192, 0.178);
}

.search-result {
  padding: 10px;
}

.search-result-icon {
  color: orange;
  margin-right: 10px;
}

.search-result-address {
  margin-left: 30px;
}

div.input-search {
  display: inline-block;
  width: 26rem;
  border: 1px solid silver;
  border-radius: 0.5rem;
  height: 2.75rem;
  margin: 5px;
}

div.datepicker {
  display: inline-block;
  border: 1px solid silver;
  border-radius: 0.5rem;
  height: 2.75rem;
  width: 260px;
  margin: 5px;
  vertical-align: top;
  text-align: left;
  padding: 6px;
  box-sizing: border-box;
}

.datepicker:hover {
  cursor: pointer;
}

.datepicker-from,
.datepicker-to {
  display: inline-block;
  width: 117px;
}

.datepicker-divider {
  display: inline-block;
  width: 1px;
  background-color: silver;
  height: 1.6rem;
  margin-left: 9px;
}

.datepicker-icon-arrows {
  float: right;
  margin-top: 5px;
  margin-right: 2px;
}

.datepicker-icon,
.persons-icon {
  display: inline-block;
}

.datepicker-info,
.persons-info {
  display: inline-block;
  font-size: 0.75rem;
  margin-left: 10px;
}

div.persons {
  display: inline-block;
  border: 1px solid silver;
  border-radius: 0.5rem;
  height: 2.75rem;
  width: 8rem;
  margin: 5px;
  vertical-align: top;
  text-align: left;
  padding: 6px;
  box-sizing: border-box;
}

.persons:hover {
  cursor: pointer;
}

div.search-button {
  display: inline-block;
  vertical-align: top;
  margin: 5px;
}

.icon {
  margin-bottom: 4px;
}

.icon.icon-left {
  margin-right: 5px;
}

.icon.icon-disabled {
  color: silver;
}

@media only screen and (max-width: 1000px) {
  div.input-search {
    display: block;
    margin: auto;
  }
}
</style>
