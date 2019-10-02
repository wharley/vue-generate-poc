<template>
  <div>
    <label>{{ label }}</label>
    <select :multiple="multi">
      <option
        v-for="option in options"
        :key="option"
      >
        {{ option }}
      </option>
    </select>
  </div>
</template>

<script>
export default {
  name: 'Select',
  props: ['multi', 'options', 'name', 'label']
}
</script>