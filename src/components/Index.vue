<template>
  <div>
    <h1 class="is-size-1">{{ msg }}</h1>
    <form-data @onEnlargeText="onEnlargeText"></form-data>
  </div>
</template>

<script>
import FormData from './Form'
export default {
  name: 'Index',
  components: {
    FormData
  },
  data () {
    return {
      msg: 'Save your money in procesing!😋',
      list: [],
      text: '',
      money: 0
    }
  },
  methods: {
    onEnlargeText (form) {
      this.text = form.text
      this.money = form.money
      console.log(this.text, this.money)
    }
  }
}
</script>
