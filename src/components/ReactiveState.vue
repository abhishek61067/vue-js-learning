
<script>
          alert("ReactiveState.vue: Only template will be rendered if the reactive state will change and reactive state are inside the data option of the component. If the whole page would be rendered, alert would be generated again when question changes.Here is where watchers comes in place.");

export default {

  data() {
    return {
      question: '',
      answer: 'Questions usually contain a question mark. ;-)'
    }
    
  },
  
 
  
}
</script>

<template>
    <p class="h2 text-primary">Reactive State</p>
  <p>
    Ask a yes/no question:
    <input v-model="question" />
  </p>
  <p>When reactive state changes, only template will be rerendered.</p>
  <p>{{ question }}</p>
</template>