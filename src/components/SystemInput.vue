<template>
  <div class="row justify-center">
    <q-input v-model="componentValue" v-bind="$attrs" style="width: 250px">
      <!--      uncomment the below line to see the error-->
      <!--      <template v-for="(_, slot) of $slots" v-slot:[slot]="scope"><slot :name="slot" v-bind="scope"/></template>-->
    </q-input>
    <q-separator class="full-width" color="secondary" />
    <div class="bg-negative full-width q-pa-lg">slots: {{ $slots }}</div>
    <div class="bg-warning full-width q-pa-lg">slots: {{ $slots.before }}</div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  inheritAttrs: false,
  name: "SystemInput",
  //------------------------------------------------------Props
  props: {
    rules: {
      type: [Object, String],
      default: "",
    },
    // must be included in props
    modelValue: {
      type: null,
    },
  },
  watch: {
    modelValue(newValue) /* change v-model from JS*/ {
      this.componentValue = newValue;
    },
    componentValue(newValue) {
      this.$emit("update:modelValue", newValue);
    },
  },
  setup(props) {
    return {
      componentValue: ref(props.modelValue),
    };
  },
};
</script>
