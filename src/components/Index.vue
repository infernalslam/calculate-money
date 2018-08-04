<template>
  <div>
    <center><h1 class="is-size-1">{{ msg }}</h1></center>
    <div class="columns">
      <div class="column">
         <form-data @onEnlargeText="onEnlargeText"></form-data>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <list-item :list="list"></list-item>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <sum :summaryData="summaryData"></sum>
      </div>
    </div>
  </div>
</template>

<script>
import FormData from './Form'
import ListItem from './ListItem'
import Sum from './Sum'
export default {
  name: 'Index',
  components: {
    FormData,
    ListItem,
    Sum
  },
  data () {
    return {
      msg: 'Calculate money  😞😤',
      list: []
    }
  },
  methods: {
    onEnlargeText (form) {
      if (form.text && (parseFloat(form.money) > 0)) {
        this.list.push(form)
      }
    }
  },
  computed: {
    summaryData () {
      if (this.list.length === 0) return 0
      return this.list.map(data => parseFloat(data.money)).reduce((accumulator, currentValue) => accumulator - currentValue)
    }
  }
}
</script>
