<template>
    <div class="mb-4">
        <div class="text-primary h2">Prop passing:</div>
{{ `this prop: ${msg} is coming from some other component` }}

<!-- {{ msg }} -->
    </div>
</template>

<script>
export default {
  props: {
    msg: String,
  },
};
</script>

