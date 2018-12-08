
<template>
  <b-table :items="cpnsList" :fields="fields"></b-table>
</template>


<script>
  import axios from 'axios';
  export default {
    data() {
      return {
        cpnsList: [],
        fields: ['nik', 'name', 'address']
      }
    },
    methods: {
      getCpns(){
        axios.get("http://localhost:8080/cpns")
        .then(response => this.cpnsList = response.data);
      }
    },
    mounted() {
      this.getCpns();
    }
  }
</script>
