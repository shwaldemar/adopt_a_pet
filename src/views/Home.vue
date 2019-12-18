<template>
  <div class="home-view-container">
    <h1>Adopt a new best friend</h1>
    <p>{{ animalsCount }} Pets up for adoption.</p>
    <p>{{ getAllCats.length }} Cats available.</p>
    <p>{{ getAllDogs.length }} Dogs available.</p>
    <button @click="togglePetForm" class="btn btn-primary">Add New Pet</button>

    <b-form @submit.prevent="handleSubmit" v-if="showPetForm">

    <b-form-group id="exampleInputGroup2" label="Pet's Name:" label-for="exampleInput2">
      <b-form-input
        id="exampleInput2"
        type="text"
        v-model="formData.name"
        required
        placeholder="Enter name"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup3" label="Species:" label-for="exampleInput3">
      <b-form-select
        id="exampleInput3"
        :options="['cats', 'dogs']"
        required v-model="formData.species"
      ></b-form-select>
    </b-form-group>

    <b-form-group id="exampleInputGroup4" label="Pet's Age:" label-for="exampleInput4">
      <b-form-input
        id="exampleInput4"
        type="number"
        v-model="formData.age"
        required
        placeholder="Enter age"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup5" label="Pet's Breed:" label-for="exampleInput5">
      <b-form-input
        id="exampleInput5"
        type="text"
        v-model="formData.breed"
        required
        placeholder="Enter breed"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup6" label="Pet's Species:" label-for="exampleInput6">
      <b-form-input
        id="exampleInput6"
        type="text"
        v-model="formData.species"
        required
        placeholder="Enter species"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup7" label="Pet's Colour:" label-for="exampleInput7">
      <b-form-input
        id="exampleInput7"
        type="text"
        v-model="formData.color"
        required
        placeholder="Enter colour"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup8" label="Gender:" label-for="exampleInput8">
      <b-form-select
        id="exampleInput8"
        type="text"
        :options="['male', 'female']"
        required v-model="formData.gender"
      ></b-form-select>
    </b-form-group>

    <b-form-group id="exampleInputGroup9" label="Pet's Weight:" label-for="exampleInput9">
      <b-form-input
        id="exampleInput9"
        type="text"
        v-model="formData.weight"
        required
        placeholder="Enter weight"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup10" label="Pet's Location:" label-for="exampleInput10">
      <b-form-input
        id="exampleInput10"
        type="text"
        v-model="formData.location"
        required
        placeholder="Enter location"
      ></b-form-input>
    </b-form-group>

    <b-form-group id="exampleInputGroup11" label="Pet's Notes:" label-for="exampleInput11">
      <b-form-input
        id="exampleInput11"
        type="text"
        v-model="formData.notes"
        required
        placeholder="Enter notes"
      ></b-form-input>
    </b-form-group>

  <b-button type="submit" variant="primary">Submit</b-button>
  <b-button type="reset" variant="danger">Reset</b-button>
</b-form>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'

export default {
  name: 'home',
  data () {
    return {
      showPetForm: false,
      formData: {
        name: '',
        age: 0,
        species: null,
        breed: '',
        color: '',
        gender: null,
        weight: 0,
        location: '',
        notes: ''
      }
    }
  },
  computed: {
    ...mapGetters(['animalsCount', 'getAllCats', 'getAllDogs'])
  },
  methods: {
    ...mapActions(['addPet']),
    togglePetForm () {
      // console.log('the logic is wrong')
      this.showPetForm = !this.showPetForm
    },
    handleSubmit () {
      const { species, name, age, breed, color, gender, weight, location, notes } = this.formData
      const payload = {
        species,
        pet: {
          name,
          age,
          breed,
          species,
          color,
          gender,
          weight,
          location,
          notes
        }
      }
      this.addPet(payload)
      this.formData = {
        name: '',
        age: 0,
        species: null,
        breed: '',
        color: '',
        gender: null,
        weight: 0,
        location: '',
        notes: ''
      }
    }
  }
}
</script>
