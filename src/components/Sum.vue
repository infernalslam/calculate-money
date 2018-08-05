<template>
  <div>
    <div class="columns">
       <div class="column is-half is-offset-one-quarter has-text-right is-size-3">
         <hr>
          <a class="button is-info" @click="submit"> เก็บเงิน </a> {{ summaryData }}
       </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['summaryData', 'saveMoney'],
  methods: {
    submit () {
      this.$emit('saveMoney', this.summaryData)
    }
  }
}
</script>
