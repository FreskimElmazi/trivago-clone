<template>
  <div class="card">
    <div class="card-image">
      <img :src="image" alt="hotel_image1" />
    </div>
    <div class="card-info">
      <h1>{{ item.name }}</h1>
      <div class="card-info-stars">
        <font-awesome-icon
          icon="fa-solid fa-star"
          style="color: orange"
          v-for="index in item.stars"
          :key="index"
        />
        <span>Hotel</span>
      </div>
      <div class="card-info-cup" v-show="item.trophy">
        <font-awesome-icon icon="fa-solid fa-trophy" />
        <span>Beliebte Wahl</span>
      </div>
      <div class="card-info-location">
        <font-awesome-icon icon="fa-solid fa-location-dot" />
        <span>{{ item.distance }} km bis Zentrum</span>
        <font-awesome-icon icon="fa-solid fa-chevron-down" class="icon" />
      </div>
      <div class="card-info-rating">
        <span class="card-info-rating-number">{{ item.rating }}</span>
        <span
          ><b>Sehr gut</b> <span>({{ item.reviews }} Bewertungen)</span></span
        >
        <font-awesome-icon icon="fa-solid fa-chevron-down" class="icon" />
      </div>
    </div>
    <div class="card-actions">
      <div class="card-actions-top">
        <div style="height: 150px">
          <div>
            <small><b>Hotels.com</b></small>
          </div>
          <font-awesome-icon
            icon="fa-solid fa-circle-check"
            class="icon-green"
          />
          <span class="text-green"
            ><small><b>Kostenlose Stornierung</b></small></span
          >
          <div>
            <small>10 Gaste, 1 Nacht fur</small>
            <span class="text-green"
              ><small
                ><b>{{ item.price }} CHF</b></small
              ></span
            >
          </div>
        </div>
        <div class="card-actions-top-price">
          <span>{{ item.price }} CHF</span>
        </div>
        <div class="card-actions-top-offer">
          <button-component buttonClass="success" size="small"
            ><b
              >Zum Angebot
              <font-awesome-icon icon="fa-solid fa-angle-right" /></b
          ></button-component>
        </div>
      </div>
      <div class="card-actions-bottom">
        <div class="card-actions-bottom-price">
          <span
            ><small><b>Booking.com</b></small></span
          >
          <div>
            <b>{{ item.price }} CHF</b>
          </div>
        </div>
        <div class="card-actions-bottom-offer">
          <span
            ><small><b>Unser niedrigster Preis: </b></small></span
          >
          <div>
            <b>957 CHF </b><span><small>Destinia</small></span
            ><font-awesome-icon icon="fa-solid fa-chevron-down" class="icon" />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ButtonComponent from "./button-component.vue";

export default {
  name: "CardComponent",
  components: {
    ButtonComponent,
  },
  props: {
    item: {
      type: Object,
      required: true,
    },
  },
  computed: {
    image() {
      return `./images/hotels/${this.item.img}`;
    },
  },
};
</script>

<style scoped>
div.card {
  width: 100%;
  height: 300px;
  border-radius: 0.5rem;
  border: 0 solid;
  box-shadow: 0 1px 4px 0 rgb(10 17 33 / 65%);
  padding: 2px;
  margin: 10px 0;
}

div.card-image {
  display: inline-block;
  max-width: 300px;
  float: left;
}

img {
  height: 300px;
  width: 100%;
  object-fit: cover;
  overflow: hidden;
  border-radius: 0.5rem;
}

div.card-info {
  display: inline-block;
  width: 45%;
  text-align: left;
  box-sizing: border-box;
  vertical-align: top;
}

.card-info-cup {
  width: 8rem;
  height: 1rem;
  padding: 1%;
  background-color: rgba(255, 209, 209, 0.397);
  margin: 9px 0 9px 0;
  border-radius: 0.1rem;
}

div.card-actions {
  display: inline-block;
  width: 30%;
  vertical-align: top;
  text-align: left;
  float: right;
}

div.card-info-rating {
  border-top: 1px solid silver;
  padding: 9px 5px 9px 5px;
}

div.card-info-rating:hover {
  cursor: pointer;
  background-color: rgba(192, 192, 192, 0.178);
}

.card-info-rating-number {
  height: 20px;
  width: 30px;
  display: inline-block;
  border-radius: 20px;
  background-color: green;
  text-align: center;
  line-height: 1.4;
  color: white;
  font-weight: bold;
}

.icon {
  float: right;
}

.icon-green {
  color: green;
  margin-right: 10px;
}

.text-green {
  color: green;
}

div.card-info-location {
  border-top: 1px solid silver;
  padding: 9px 5px 9px 5px;
}

div.card-info-location:hover {
  cursor: pointer;
  background-color: rgba(192, 192, 192, 0.178);
}

div.card-info-stars {
  padding-bottom: 9px;
}

div.card-actions-top {
  height: 200px;
  padding: 10px;
  border-radius: 0.75rem;
  margin: 2px;
  background-color: rgba(2, 252, 2, 0.075);
  box-sizing: border-box;
  margin: 1%;
}

.card-actions-top:hover {
  border: 1px solid green;
  cursor: pointer;
}

.card-actions-top-offer,
.card-actions-top-price {
  display: inline-block;
}

.card-actions-top-price span {
  font-size: 20px;
  font-weight: bold;
  color: green;
}

.card-actions-top-offer {
  float: right;
}

.card-actions-bottom-price {
  border: 1px solid silver;
  border-radius: 0.5rem;
  display: inline-block;
  height: 55px;
  width: 28%;
  box-sizing: border-box;
  margin: 1%;
  padding: 1%;
}

.card-actions-bottom-price:hover {
  cursor: pointer;
  background-color: rgba(192, 192, 192, 0.178);
}

.card-actions-bottom-offer {
  border: 1px solid silver;
  border-radius: 0.5rem;
  display: inline-block;
  height: 55px;
  width: 68%;
  box-sizing: border-box;
  margin: 1%;
  padding: 1%;
}

.card-actions-bottom-offer:hover {
  cursor: pointer;
  background-color: rgba(192, 192, 192, 0.178);
}

@media only screen and (max-width: 1000px) {
  div.card-info {
    display: block;
    margin: auto;
  }
  div.card-actions {
    display: block;
    margin: auto;
  }
}
</style>
