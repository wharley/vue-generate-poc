<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <FormGenerator
      :schema="schema"
      v-model="formData"
    />
  </div>
</template>

<script>
import FormGenerator from '@/components/FormGenerator'
import schema from '@/schema-form/schema'

export default {
  name: 'app',
  components: {
    FormGenerator
  },
  data() {
    return {
      formData: {
        firstName: 'Form generator'
      },
      schema: [
        {
          fieldType: 'Select',
          name: 'title',
          multi: false,
          label: 'Title',
          options: ['Ms', 'Mr', 'Mx', 'Dr', 'Madam', 'Lord']
        },
        {
          fieldType: 'Input',
          placeholder: 'First Name',
          label: 'First Name',
          name: 'firstName',
          type: 'text'
        },
        {
          fieldType: 'Input',
          placeholder: 'Last Name',
          label: 'Last Name',
          name: 'lastName',
          type: 'text'
        },
        {
          fieldType: 'Input',
          placeholder: 'Age',
          name: 'age',
          label: 'Age',
          type: 'number',
          minValue: 0
        }
      ]
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
