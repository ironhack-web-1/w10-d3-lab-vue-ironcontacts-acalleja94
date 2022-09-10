

<template>
  <h1 class="display-1">IronContacts</h1>

<div class="container">
  <table class="table table-hover">
    <thead class="thead-dark">
        <tr>
            <th class="col">Picture</th>
            <th class="col">Name</th>
            <th class="col">Popularity</th>
            <th class="col">Won an Oscar</th>
            <th class="col">Won an Emmy</th>
        </tr>
    </thead>

    <tbody>
        <tr v-for="(element, index) of ListOfContacts" :key="index">
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
        ListOfContacts: [
          {
            name: "Idris Elba",
            pictureUrl:
              "https://image.tmdb.org/t/p/w500/d9NkfCwczP0TjgrjpF94jF67SK8.jpg",
            popularity: 11.622713,
            id: "11731993-0604-4bee-80d5-67ad845d0a38",
            wonOscar: false,
            wonEmmy: false,
          },
          {
            name: "Johnny Depp",
            pictureUrl:
              "https://image.tmdb.org/t/p/w500/kbWValANhZI8rbWZXximXuMN4UN.jpg",
            popularity: 15.656534,
            id: "7dad00f7-3949-477d-a7e2-1467fd2cfc06",
            wonOscar: false,
            wonEmmy: false,
          },
          {
            name: "Monica Bellucci",
            pictureUrl:
              "https://image.tmdb.org/t/p/w500/qlT4904d8oi2NIs28RrgnIZDFZB.jpg",
            popularity: 16.096436,
            id: "0ad5e441-3084-47a1-9e9b-b917539bba71",
            wonOscar: true,
            wonEmmy: false,
          },
          {
            name: "Gal Gadot",
            pictureUrl:
              "https://image.tmdb.org/t/p/w500/34kHAyBaBhq2kUrmhM15paEBuuI.jpg",
            popularity: 10.049256,
            id: "b497e3c4-50bb-4ae2-912f-eb36802c5bc2",
            wonOscar: false,
            wonEmmy: true,
          },
          {
            name: "Ian McKellen",
            pictureUrl:
              "https://image.tmdb.org/t/p/w500/coWjgMEYJjk2OrNddlXCBm8EIr3.jpg",
            popularity: 10.070132,
            id: "0067ae32-97b6-4431-898e-eb1c10150abb",
            wonOscar: false,
            wonEmmy: false,
          },
        ],
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

.container{
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>

