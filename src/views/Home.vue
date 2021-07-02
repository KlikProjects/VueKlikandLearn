<template>
  <div class="home">
    <h1 class="titlePage">Card de los Eventos</h1>
    <br />

    <EventCard @myEvent="showSubscribers" />
    <Subscribers :id="eventId" />
    
    <br />
  </div>
</template>

<script>
// @ is an alias to /src

import EventCard from "@/components/EventCard.vue";
import Subscribers from "../components/Subscribers.vue";

export default {
  name: "Home",
  components: {
    EventCard,
    Subscribers,
  },
  data() {
    return {
      eventId: null
    }
  },
  methods: {
    showSubscribers(id) {
      let getCardList = document.querySelector('.cardContainer');
      getCardList.classList.add('hidden');

      let getSubscribersList = document.querySelector('.subscribers');
      getSubscribersList.classList.remove('hidden');

      return this.eventId = id;
    },
  },
};
</script>

<style lang="scss">

.hidden {
  display: none;
}

</style>