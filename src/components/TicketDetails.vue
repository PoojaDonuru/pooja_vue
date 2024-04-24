<template>
  <div class="ticket-details">
    <h2>Ticket Details</h2>
    <p>Ticket Number: {{ ticket.TicketNumber }}</p>
    <p>Ticket Price: {{ ticket.TicketPrice }}</p>
    <p>Source: {{ ticket.Source }}</p>
    <p>Destination: {{ ticket.Destination }}</p>
    <p>Date of Journey: {{ ticket.DateOfJourney }}</p>
    <p>Duration of Journey: {{ ticket.DurationOfJourney }}</p>
    <p>Mode of Transport: {{ ticket.ModeOfTransport }}</p>
    <button @click="closeDetails">Close</button>
  </div>
</template>

<script>
export default {
  props: ['ticket'],
  methods: {
    closeDetails() {
      this.$emit('close');
    }
  }
};
</script>

<style>
.ticket-details {
  background-color: #0A2463;
  padding: 20px;
  border-radius: 5px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
.ticket-details h2 {
  margin-top: 0;
}
.ticket-details button {
  margin-top: 10px;
  padding: 5px 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 3px;
  cursor: pointer;
}
.ticket-details button:hover {
  background-color: #0056b3;
}
</style>
