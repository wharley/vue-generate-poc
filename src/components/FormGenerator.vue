<template>
  <div>
    <component v-for="(field, index) in schema"
               :key="index"
               :is="field.fieldType"
               :value="formData[field.name]"
               @input="updateForm(field.name, $event)"
               v-bind="field">
    </component>
  </div>
</template>

<script>
import Input from '@/components/Input.vue'
import Select from '@/components/Select.vue'

export default {
  name: "FormGenerator",
  components: { Select, Input },
  props: ['schema', 'value'],
  data() {
    return {
      formData: this.value || {}
    };
  },
  methods: {
    updateForm(fieldName, value) {
      this.$set(this.formData, fieldName, value);
      this.$emit('input', this.formData)
    }
  }
};
</script>