<template>
  <fieldset id="form-wrapper">
    <legend>{{ heading }}</legend>
    <form @submit.prevent="display">
      <UserInput v-model="name" :placeholder="enterName"/>
      <UserInput v-model="surname" :placeholder="enterSurname"/>
      <label> {{ result }}</label>
      <button>Submit</button>
    </form>
  </fieldset>

</template>

<script>
import UserInput from './components/InputComponent.vue'

export default {
  name: 'App',
  components: {
    UserInput
  },
  data() {
    return {
      heading: 'Please fill in your details',
      name: '',
      surname: '',
      enterName: 'Enter your name',
      enterSurname: 'Enter your surname',
      result: ''
    }
  },
  methods: {
    display() {
      this.result = `${this.name} ${this.surname}`;
    }
  }
}
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
</style>
