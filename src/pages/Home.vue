<template>
  <div id="app">
        <h1>Marvel Movie API</h1>
        <div>
            <table>
                <thead>
                    <tr>
                    <th>ID</th>
                    <th>Poster</th>
                    <th>Title</th>
                    <th>Popularity</th>
                    <th>Rating</th>
                    <th>Release Date</th>
                    <th>Action</th>
                    </tr>
                </thead>
                <GetApi v-for="(item, index) in films"  :key="index" :item="item"></GetApi>
            </table>
        </div> 
  </div>
</template>

<script>
  import axios from 'axios'
  import GetApi from '../components/GetApi'
  export default {
    name: 'home',
    components: {    
      GetApi
    },
    computed:{
      films () {
        return this.$store.state.home.data.films 
      }
    },
    mounted: function () {
       console.log(this.$store.dispatch('home/getFilms'))
       this.$store.dispatch('home/getFilms')
    }
  }
</script>

