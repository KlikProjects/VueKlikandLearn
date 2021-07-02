<template>
  <div class="home">
    <h1 class="titlePage">Card de los Eventos</h1>
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
