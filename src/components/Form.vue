<template>
  <div>
    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <div class="field is-grouped">
           <p class="control is-expanded">
              <input class="input" type="text" placeholder="list" v-model="text">
           </p>
            <p class="control">
              <input class="input" type="number" placeholder="How much!" v-model="money" @keyup.enter="submit">
            </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['onEnlargeText'],
  data () {
    return {
      text: '',
      money: 0
    }
  },
  methods: {
    submit () {
      this.$emit('onEnlargeText', { text: this.text, money: this.money })
    }
  }
}
</script>
