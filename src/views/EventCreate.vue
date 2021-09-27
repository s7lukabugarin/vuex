<template>
  <div>
    <h1>Create Event, {{ user.name }} {{ userID }}</h1>
    <p>This was created by {{ user.id }}</p>
    <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ducimus, laborum? {{ catLength }}</p>
    <ul>
      <li v-for="cat in categories" :key="cat">
        {{ cat }}
      </li>
    </ul>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex';

export default {
  computed: {
    ...mapState(['user', 'categories']),
    ...mapGetters(['catLength']),
    catLength() {
      return this.$store.getters.catLength;
    },
    userName() {
      return this.$store.state.user.name;
    },
    userID() {
      return this.$store.state.user.id;
    }
  }
}
</script>
