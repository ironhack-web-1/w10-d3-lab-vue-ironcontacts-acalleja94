

<template>
  <h1 class="display-1 text-primary">IronContacts</h1>

<div class="container container__pos">
  <table class="table table-hover">
    <thead>
        <tr>
            <th class="col col__style">Picture</th>
            <th class="col col__style">Name</th>
            <th class="col col__style">Popularity</th>
            <th class="col col__style">Won an Oscar</th>
            <th class="col col__style">Won an Emmy</th>
        </tr>
    </thead>

    <tbody>
        <tr v-for="(element, index) of contactSorted" :key="index">
            <td scope="row">
              <img
              :src="element.pictureUrl"
              :alt="element.name + ` image`"
              class="image"
            />
            </td>
            <td> {{ element.name }}</td>
            <td>{{ element.popularity }}</td>
            <td>{{ wonAward(element.wonOscar) }}</td>
            <td>{{ wonAward(element.wonEmmy) }}</td>
        </tr>
    </tbody>
  </table>
</div>
  
</template>

<script>
  import contacts from "./contacts.json";
  
  export default {
    data() {
      return {
        contactList: contacts,
        contactSorted: contacts.slice(0, 5),
      };
    },
    methods: {
      wonAward(element) {
        if (element === true || element === true){
          return "🏆";
        } else {
          return "❌";
        }
      }
    },
  };
  </script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.image{
  width: 80px;
  height: auto;
}

.col__style {
  text-transform: uppercase;
}

.container__pos{
  margin-top: 50px;
}

</style>

