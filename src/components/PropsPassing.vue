<template>
    <div class="mb-4">
        <p class="text-primary fs-6">Prop passing:</p>
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

