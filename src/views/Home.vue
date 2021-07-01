<template>
  <div class="home">
    <h1>Card de los Eventos</h1>
    <br />

    <EventCard/>
    <Subscribers/>
    
    <br />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import EventCard from "@/components/EventCard.vue";
import Subscribers from '../components/Subscribers.vue';

export default {
  name: "Home",
  components: {
    HelloWorld,
    EventCard,
    Subscribers,
  },
/*   data() {
    return {
      events: [],
    };
  }, */
  methods: {
    changetext() {
      this.text = "Hola coders despues de click";
    },
    clickShow(id) {
      <router-link to="/Show/id"> </router-link>;
    },
  },
 /*  mounted() {
    axios.get("http://127.0.0.1:8000/api/events").then((response) => {
      this.events = response.data;
    });
  }, */
};
</script>
