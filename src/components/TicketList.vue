<template>
  <div class="ticket-list">
    <div v-for="ticket in tickets" :key="ticket.TicketNumber" class="ticket-card" @click="showDetails(ticket)">
      <h2>Ticket Number: {{ ticket.TicketNumber }}</h2>
      <p>Ticket Price: {{ ticket.TicketPrice }}</p>
      <p>Source: {{ ticket.Source }}</p>
      <p>Destination: {{ ticket.Destination }}</p>
      <p>Date of Journey: {{ ticket.DateOfJourney }}</p>
      <p>Duration of Journey: {{ ticket.DurationOfJourney }}</p>
      <p>Mode of Transport: {{ ticket.ModeOfTransport }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TicketList',
  props: ['tickets'],
  methods: {
    showDetails(ticket) {
      this.$emit('show-details', ticket);
    }
  }
};
</script>

<style>
.ticket-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-gap: 20px;
}
.ticket-card {
  background-color: #F8F9FA;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  cursor: pointer;
}
.ticket-card h2 {
  margin-top: 0;
}
</style>
