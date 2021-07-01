<template>
  <div class="home">
    <h1>Card de los Eventos</h1>
    <br />

    <EventCard @myEvent="alertTest"/>
   
    <Subscribers />
   

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
  methods: {
    changetext() {
      this.text = "Hola coders despues de click";
    },
    clickShow(id) {
      <router-link to="/Show/id"> </router-link>;
    },
    alertTest(id){
      alert (id)

    },
  },
};
</script>
