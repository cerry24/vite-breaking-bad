<script>
import axios from 'axios';
import { store } from './store.js';

import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';

export default {
  components: {
    AppHeader,
    AppMain
  },

  data() {
    return {
      store,
      apiUrl: 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0'
    }
  },

  methods: {
    getCards(archetypeName) {
      axios.get(this.apiUrl, {
        params: {
          archetype: archetypeName
        }
      })
        .then((response) => {
          console.log(response.data.data);
          this.store.cardsList = response.data.data;
        })
        .catch(function (error) {
          console.log(error);
        })
    }
  },

  created() {
    this.getCards()
  }
}
</script>

<template>
  <header>
    <AppHeader @filter="getCards" />
  </header>

  <main>
    <AppMain />
  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use './styles/partials/variables' as *;
</style>
