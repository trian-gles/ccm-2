<script>
      import performances from '../../static/performances.json'
      import PerformanceCard from '../components/PerformanceCard.vue';
import PerformanceCard from '../components/PerformanceCard.vue';

      const today = Date.now();
      const pastPerformances = performances.filter(p => Date(p.date).getTime() < today);
      const upcomingPerformances = performances.filter(p => !pastPerformances.includes(p));

      export default{
    data() {
        return {
            pastPerformances,
            upcomingPerformances
        };
    },
    components: { PersonCard, PerformanceCard }
}
</script>

<template>
  <div class="about">
    <h1>This is the performances page</h1>
    <h2>Upcoming Events</h2>
    <PerformanceCard 
      v-for="p in upcomingPerformances"
      v-bind="p"
    />
    <h2>Past Events</h2>
    <PerformanceCard 
      v-for="p in pastPerformances"
      v-bind="p"
    />
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
