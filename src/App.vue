<!-- <script setup> -->


 <script>

export default{
  data() {
    return {
      childMsg: 'No child msg yet'
    }
  },
 components: {
   EmitVue,
   AttributeBinding,
   ListRendering ,
   PropsPassing,
   ReactiveState,
   WatchersVue,
   ComputedVue,
   RefVue,
  }
}  

import EmitVue from './components/EmitVue.vue';
import AttributeBinding from './components/AttributeBinding.vue';
import ListRendering from './components/ListRendering.vue';
import PropsPassing from './components/PropsPassing.vue';
import ReactiveState from './components/ReactiveState.vue';
import WatchersVue from './components/WatchersVue.vue';
import ComputedVue from './components/ComputedVue.vue';
import RefVue from './components/RefVue.vue';

</script>

<template>
  <AttributeBinding/>
<EmitVue @response="(msg) => childMsg = msg" />
<p > {{ childMsg }}</p>
<PropsPassing msg="test-prop" />
<ListRendering/>
<ReactiveState/>
<WatchersVue/>
<ComputedVue/>
<RefVue/>

</template>


