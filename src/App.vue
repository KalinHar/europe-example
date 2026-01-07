<template>
  <PropsSelector 
    @selectCriteria="selectCriteria"
    @selectTonality="selectTonality"
    @selectHover="selectHover"
    @selectSelect="selectSelect">
  </PropsSelector>
  <EuropeMap
    :criteria="criteria"
    :tonality="tonality"
    :hoverColor="hoverColor"
    :selectedColor="selectedColor"
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
      tonality: 'blue',
      hoverColor: 'aqua',
      selectedColor: 'aqua'
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
    },
    selectHover(selected) {
      this.hoverColor = selected;
    },
    selectSelect(selected) {
      this.selectedColor = selected;
    }
  }
}
</script>


<style>
</style>
