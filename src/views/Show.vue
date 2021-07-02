<template>
  <div class="show">
    <h1>Inscrito a este Evento</h1>
    <br />

    
      <div v-for="user in users" v-bind:key="user">
        
          <div>{{ user.name }}</div>
        
      </div>
    
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import axios from "axios";

export default {
  name: "Home",
  components: {
    HelloWorld,
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    changetext() {
      this.text = "Hola coders despues de click";
    },
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
