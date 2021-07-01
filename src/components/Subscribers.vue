<template>
  <div class="Subscribers">
    <h1>Inscrito a este Evento</h1>
    <br />

    
      <div v-for="user in users" v-bind:key="user">
        
          <div>{{ user.name }}</div>
        
      </div>
    
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Subscribers",
  props: {
    id: Number,
  },
  data() {
    return {
      users: [],
    };
  },
  mounted() {
    axios
      .get(`http://127.0.0.1:8000/api/events/1/subscribers`)
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
