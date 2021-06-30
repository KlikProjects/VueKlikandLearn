<template>
  <div class="home">
    <!--     <h1 @click="changetext">{{ text }}</h1>
    <div v-for="event in list">
      {{ event.id }}
      {{ event.nombre }}
    </div> -->
    <h1>Card de los Eventos</h1>
    <br />
    <div class="cardContainer">
      <div v-for="event in events">
        <EventCard
          v-bind:title="event.title"
          v-bind:description="event.description"
          v-bind:date_time="event.date_time"
          v-bind:image="event.image"
        />
        <br />
      </div>
    </div>

    <!--     <div v-for="event in events">
      <ul>
        <li>
          <img
            :src="event.image"
            class="img-responsive"
            height="50%"
            width="50%"
          />
        </li>
        <li>{{ event.title }}</li>
        <li>{{ event.date_time }}</li>
        <li>{{ event.description }}</li>
        <li><button>Show</button></li>
      </ul>
    </div> -->
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import axios from "axios";
import EventCard from "@/components/EventCard.vue";

export default {
  name: "Home",
  components: {
    HelloWorld,
    EventCard,
  },
  data() {
    return {
      /* text: "Hola Coders desde la data",
      list: [
        {
          id: 1,
          nombre: "manzana",
        },
        {
          id: 2,
          nombre: "pera",
        },
        {
          id: 3,
          nombre: "platano",
        },
      ], */
      events: [],
    };
  },
  methods: {
    changetext() {
      this.text = "Hola coders despues de click";
    },
  },
  mounted() {
    axios.get("http://127.0.0.1:8000/api/events").then((response) => {
      this.events = response.data;
    });
  },
};
</script>
