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
/* .logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
} */
</style>
