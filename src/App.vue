<template>
  <div id="app">
    <h1>Online Ticketing System</h1>
    <TicketList :tickets="tickets" @show-details="showDetails" />
    <TicketDetails v-if="selectedTicket" :ticket="selectedTicket" @close="closeDetails" />
    <AppFooter />
  </div>
</template>

<script>
import axios from 'axios';
import TicketList from './components/TicketList.vue';
import TicketDetails from './components/TicketDetails.vue';
import AppFooter from './components/AppFooter.vue';

export default {
  name: 'App',
  components: {
    TicketList,
    TicketDetails,
    AppFooter
  },
  data() {
    return {
      tickets: [],
      selectedTicket: null
    };
  },
  async created() {
    try {
      const response = await axios.get('https://pooja-node.onrender.com/api');
      this.tickets = response.data;
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  },
  methods: {
    showDetails(ticket) {
      this.selectedTicket = ticket;
    },
    closeDetails() {
      this.selectedTicket = null;
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #FFD700;
}
h1 {
  text-align: center;
}
</style>
