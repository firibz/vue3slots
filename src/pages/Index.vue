<template>
  <q-page class="flex flex-center column">
    <system-input filled v-model="text" label="in child">
      <template v-slot:before>
        <q-icon name="mail" />
      </template>
      <template v-slot:after>
        <q-icon name="person" />
      </template>
    </system-input>
    <q-input filled v-model="text2" label="in parent">
      <template v-slot:before>
        <q-icon name="mail" />
      </template>
      <template v-slot:after>
        <q-icon name="person" />
      </template>
    </q-input>
  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue';
import SystemInput from 'components/SystemInput';

export default defineComponent({
  name: 'PageIndex',
  components: { SystemInput },
  setup() {
    return {
      text: ref(''),
      text2: ref(''),
    };
  },
});
</script>
