<template>
  <div class="subscribers hidden">
    <h1>Inscrito a este Evento {{ id }}</h1>
    <br />
    <div v-for="user in users">
      <div>{{ user.name }}</div>
    </div>
    <button @click="hideSubscribers" class="btn btn-primary">Go back</button>
  </div>
</template>

<script>
import axios from 'axios';
import EventCard from '@/components/EventCard.vue';
import Home from '@/views/Home.vue';

/* console.log(Home.data().events); */

export default {
  name: "Subscribers",
  props: {
    id: Number,
  },
  components: {
    EventCard,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    hideSubscribers() {
      let getSubscribersList = document.querySelector(".subscribers");
      getSubscribersList.classList.add("hidden");

      let getCardList = document.querySelector(".cardContainer");
      getCardList.classList.remove("hidden");
    },
  },
  mounted() {
    axios
      .get(`http://127.0.0.1:8000/api/events/4/subscribers`)
      .then((response) => {
        this.users = response.data;
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
</style>
