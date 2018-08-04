<template>
  <div>
    <center><h1 class="is-size-1">{{ msg }}</h1></center>
    <form-data @onEnlargeText="onEnlargeText"></form-data>
    <list-item :list="list"></list-item>
  </div>
</template>

<script>
import FormData from './Form'
import ListItem from './ListItem'
export default {
  name: 'Index',
  components: {
    FormData,
    ListItem
  },
  data () {
    return {
      msg: 'Save your money in procesing!😋',
      list: []
    }
  },
  methods: {
    onEnlargeText (form) {
      if (form.text && (parseFloat(form.money) > 0)) {
        this.list.push(form)
      }
    }
  }
}
</script>
