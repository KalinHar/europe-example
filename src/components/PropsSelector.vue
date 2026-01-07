<template>
    <div style="display: inline-flex; gap: 1rem; padding: 1rem;">
        <div>
            <label style="margin-inline-end: 0.5rem;">Criteria</label>
            <select style="width: 10rem;" v-model="criteria" @change="$emit('selectCriteria', criteria)">
                <option v-for="value in criteries" :key="value" :value="value">
                    {{ value }}
                </option>
            </select>
        </div>
        <div>
            <label style="margin-inline-end: 0.5rem;">Tonality</label>
            <select style="width: 5rem;" v-model="tonality" @change="$emit('selectTonality', tonality)">
                <option v-for="value in tonalities" :key="value" :value="value">
                    {{ value }}
                </option>
            </select>
        </div>
        <div>
            <label style="margin-inline-end: 0.5rem;">Hover</label>
            <select style="width: 5rem;" v-model="hoverColor" @change="$emit('selectHover', hoverColor)">
                <option v-for="value in fillColors" :key="value" :value="value">
                    {{ value }}
                </option>
            </select>
        </div>
        <div>
            <label style="margin-inline-end: 0.5rem;">Selected</label>
            <select style="width: 5rem;" v-model="selectColor" @change="$emit('selectSelect', selectColor)">
                <option v-for="value in fillColors" :key="value" :value="value">
                    {{ value }}
                </option>
            </select>
        </div>
    </div>
    
</template>

<script>
export default {
    props: {
        tooltipOffset: {
            type: Object,
            default: {
                x: -70,
                y: -60
            }
        }
    },
    data() {
        return {
            criteries: ['internetSpeed', 'population', 'area', 'averagePopulationAge'],
            criteria: 'internetSpeed',
            tonalities: ['blue', 'red', 'green', 'orange', 'dark', 'light'],
            tonality: 'blue',
            fillColors: ['aqua', 'silver', 'grey', 'violet', 'teal', 'olive', 'pink', 'tan', 'magenta', 'black', 'white'],
            selectColor: 'aqua',
            hoverColor: 'aqua'
        };
    },
    watch: {

    },
    computed: {

    },
    methods: {

    }
};
</script>

<style scoped></style>
