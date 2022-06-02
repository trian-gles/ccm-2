

<script>
      import people from '../../static/people.json'
      import PersonCard from '@/components/PersonCard.vue'
      
      export default{
    data() {
        return {
            faculty: people.faculty,
            assistants: people.assistants,
            members: people.members,
            alumni: people.alumni
        };
    },
    components: { PersonCard }
}
</script>

<template>
  <div class="about">
    <h1>This is the people page</h1>
    <h2>Faculty</h2>
    <PersonCard
      v-for="person in faculty"
      v-bind="person"
    />
    <h2>Assistants</h2>
    <div v-for="person in assistants">{{person}}</div>
    <h2>Members</h2>
    <div v-for="person in members">{{person}}</div>
    <h2>Alumni</h2>
    <div v-for="person in alumni">{{person}}</div>
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
