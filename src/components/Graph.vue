<template>
  <div>
    <div class="columns">
      <div class="column is-half is-offset-one-quarter has-text-right is-size-3">
        <vuejs-heatmap :entries="entries" :color-range="['#ecedf0', '#20452b']"></vuejs-heatmap>
      </div>
    </div>
  </div>
</template>

<script>
import VuejsHeatmap from 'vuejs-heatmap'
export default {
  components: {
    VuejsHeatmap
  },
  props: ['entries']
}
</script>
