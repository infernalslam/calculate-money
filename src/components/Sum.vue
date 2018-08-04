<template>
  <div>
    <div class="columns">
       <div class="column is-half is-offset-one-quarter has-text-right is-size-3">
         <hr>
          {{ summaryData }}
       </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['summaryData']
}
</script>
