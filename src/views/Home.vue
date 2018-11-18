<template>
  <div class="home">
    <h1>Add someone else</h1>
    <div>
      Name: <input type="text" v-model="newPersonName">
      Bio: <input type="text" v-model="newBio">
      <button v-on:click="createPerson()">Create a new famous person!</button>
    </div>
    <h1>My People</h1>
    <div v-for="person in famousPeople">
    <h2>{{ person.importantPeople }}</h2>
    <h3>{{ person.bio }}</h3>
    </div>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      newPersonName: "",
      newBio: "",
      famousPeople: [
        {
          id: 1,
          importantPeople: "Ashley",
          bio: "adjksahd laksdj alsjd sdkj laksjdieo dfjlsdjflaksdf ksdljeiw"
        },
        {
          id: 1,
          importantPeople: "Brittany",
          bio: "adjksahd laksdj alsjd sdkj laksjdieo dfjlsdjflaksdf ksdljeiw"
        },
        {
          id: 1,
          importantPeople: "Melanie",
          bio: "adjksahd laksdj alsjd sdkj laksjdieo dfjlsdjflaksdf ksdljeiw"
        }
      ]
    };
  },
  created: function() {},
  methods: {
    createPerson: function() {
      let newPerson = {
        
      }
      this.newPersonName, this.newBio;
    }
  },
  computed: {}
};
</script>