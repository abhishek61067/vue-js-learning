<script setup>
import ListRendering from './components/ListRendering.vue';
import PropsPassing from './components/PropsPassing.vue';
import ReactiveState from './components/ReactiveState.vue';
import WatchersVue from './components/WatchersVue.vue';
import ComputedVue from './components/ComputedVue.vue';

</script>

<template>
<PropsPassing msg="test-prop" />
<ListRendering/>
<ReactiveState/>
<WatchersVue/>
<ComputedVue/>

</template>


