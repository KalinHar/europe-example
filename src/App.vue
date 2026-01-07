<template>
  <PropsSelector @selectCriteria="selectCriteria" @selectTonality="selectTonality"></PropsSelector>
  <EuropeMap
    :criteria="criteria"
    :tonality="tonality"
    :propsValuesDecorators="decorators">
  </EuropeMap>
</template>

<script>
import EuropeMap from './components/EuropeMap.vue';
import PropsSelector from './components/PropsSelector.vue';

export default {
  name: 'App',
  components: {
    EuropeMap,
    PropsSelector
  },
  data() {
    return {
      criteria: 'internetSpeed',
      tonality: 'blue'
    }
  },
  computed: {
    decorators() {
      return {
        area: {suffix: " km²"},
        internetSpeed: {suffix: " Mb/s"}
      };
    }
  },
  methods: {
    selectCriteria(selected) {
      this.criteria = selected;

    },
    selectTonality(selected) {
      this.tonality = selected;
    }
  }
}
</script>


<style>
</style>
