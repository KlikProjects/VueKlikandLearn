<template>
  <div class="card" style="width: 18rem;">
    <img :src="image" class="card-img-top" alt="..." />
    <div class="card-body">
      <h5 class="card-title">{{ title }}</h5>
      <p class="card-text">{{ description }}</p>
    </div>
    <ul class="list-group list-group-flush">
      <li class="list-group-item">{{ date_time }}</li>
    </ul>
    <ul class="list-group list-group-flush">
      <router-link to="/Show">
        <button role="button" class="btn btn-outline-primary btn-sm">
          Show
        </button>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: "EventCard",
  props: {
    title: String,
    description: String,
    date_time: String,
    image: String,
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
