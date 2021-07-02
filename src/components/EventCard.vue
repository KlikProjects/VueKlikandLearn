<template>
  <div class="cardContainer">
    <div v-for="event in events" v-bind:key="event">
      <div class="card" style="width: 18rem;">
        <img :src="event.image" class="card-img-top" alt="..." />
        <div class="card-body">
          <h5 class="card-title">{{ event.title }}</h5>
          <h5 class="card-title">id : {{ event.id }}</h5>
          <p class="card-text">{{ event.description }}</p>
        </div>
        <ul class="list-group list-group-flush">
          <li class="list-group-item">{{ event.date_time }}</li>
        </ul>
        <ul class="list-group list-group-flush">
          <button
            @click="showInscribers(event.id)"
            role="button"
            class="btn btn-outline-primary btn-sm"
          >
            Show
          </button>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>

import axios from "axios";

export default {
  name: "EventCard",
  data() {
    return {
      events: [],
    };
  },
  methods:{
    showInscribers(id){
      this.$emit('myEvent', id)
    }
  },
  mounted() {
    axios.get("http://127.0.0.1:8000/api/events").then((response) => {
      this.events = response.data;
    });
  },
};
</script>

<style lang="scss">
.cardContainer {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
}

.card{
  width: 18rem;
  height: 30rem;
  background-color: #343F55;
}

.card-img-top.img{
  width: 18rem;
  height: 8rem;
}
@supports(object-fit: cover){
    .img{
    object-fit: cover;
    object-position: center center;
    }
}

.card-title{
  color: #ED554D;
}

.date{
  background-color: #343F55;
  color: #ED554D;
}
</style>
