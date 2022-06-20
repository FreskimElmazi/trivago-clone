<template>
  <div :class="topnavClass" id="myTopnav">
    <img src="./../assets/images/logo.png" alt="logo" style="float: left" />
    <a href="#language">DE</a>
    <a href="#currency">CHF</a>
    <a href="#menu">Menu</a>
    <a href="#einlogen">Einlogen</a>
    <a href="javascript:void(0);" class="icon" @click="toggle()">
      <font-awesome-icon icon="fa-solid fa-bars" />
    </a>
  </div>
</template>

<script>
export default {
  name: "NavigationBar",
  data() {
    return {
      topnavClass: 'topnav',
    };
  },
  methods: {
    toggle() {
      this.topnavClass === "topnav"
        ? (this.topnavClass += " responsive")
        : (this.topnavClass = "topnav");
    },
  },
};
</script>

<style scoped>
.topnav {
  background-color: #fff;
  overflow: hidden;
}

.topnav a {
  float: right;
  display: block;
  color: #000;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
}

.topnav a:hover {
  background-color: #ddd;
  color: black;
}

.topnav .icon {
  display: none;
}

@media screen and (max-width: 600px) {
  .topnav a:not(:first-child) {
    display: none;
  }
  .topnav a.icon {
    float: right;
    display: block;
  }
}

@media screen and (max-width: 600px) {
  .topnav.responsive {
    position: relative;
  }
  .topnav.responsive a.icon {
    position: absolute;
    right: 0;
    top: 0;
  }
  .topnav.responsive a {
    float: none;
    display: block;
    text-align: left;
  }
}
</style>
