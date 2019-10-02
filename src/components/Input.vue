<template>
  <div>
    <label>{{ label }}</label>
    <input
      :type="type"
      :name="name"
      :value="value"
      @input="$emit('input', $event.target.value)"
      :placeholder="placeholder"
    />
  </div>
</template>

<script>
export default {
  name: 'Input',
  props: ['placeholder', 'label', 'name', 'type', 'value']
}
</script>