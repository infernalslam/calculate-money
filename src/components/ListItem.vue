<template>
  <div>
    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        {{ list }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['list']
}
</script>
