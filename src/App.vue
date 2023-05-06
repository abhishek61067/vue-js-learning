<!-- <script setup> -->


 <script>

export default{
  data() {
    return {
      childMsg: 'No child msg yet',
      slot:"String: Slot is used for dynamic data passing unlike props which was statically typed."
    }
  },
 components: {
   SlotVue,
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
import SlotVue from './components/SlotVue.vue';
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
<PropsPassing msg="test-prop" />
<EmitVue @response="(msg) => childMsg = msg" />    <!-- this will change the childMsg state -->
<p > {{ childMsg }}</p>    <!-- Now we are accessing the cihldMsg which has been changed by emitted response -->
<div class="h2 text-primary">Slot:</div>
<SlotVue></SlotVue>
<SlotVue>{{ slot }}</SlotVue>
<SlotVue><h1>h1: Slot is used for dynamic data passing which we could not do from prop passing</h1></SlotVue>
<ListRendering/>
<ReactiveState/>
<WatchersVue/>
<ComputedVue/>
<RefVue/>

</template>


