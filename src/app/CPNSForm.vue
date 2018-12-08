<template>
  <b-container>
    <b-row class="my-1">
      <b-col sm="3">
        <label for="nik">NIK</label>
      </b-col>
      <b-col sm="9">
        <b-form-input id="nik" type="text" v-model="form.nik"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="3">
        <label for="name">Nama</label>
      </b-col>
      <b-col sm="9">
        <b-form-input id="name" type="text" v-model="form.name"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="3">
        <label for="address">Alamat</label>
      </b-col>
      <b-col sm="9">
        <b-form-input id="address" type="text" v-model="form.address"></b-form-input>
      </b-col>
    </b-row>
    <b-row class="my-1">
      <b-col sm="3">
        <label for="myaction"></label>
      </b-col>
      <b-col sm="9">
        <b-button v-on:click="saveCpns()">Simpan</b-button>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
  import axios from 'axios';
  export default {
    data() {
      return {
        form: {}
      }
    },
    methods: {
      saveCpns() {
        axios.post("http://localhost:8080/cpns", this.form)
        .then(response => {
          console.log(response.data);
          alert("berhasil");
        });
      }
    }
  }
</script>
