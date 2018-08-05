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
        <sum :summaryData="summaryData" @saveMoney="saveMoney"></sum>
      </div>
    </div>
    <div class="columns">
      <div class="column">
        <graph :entries="entries"></graph>
      </div>
    </div>
  </div>
</template>

<script>
import FormData from './Form'
import ListItem from './ListItem'
import Sum from './Sum'
import Graph from './Graph'
export default {
  name: 'Index',
  components: {
    FormData,
    ListItem,
    Sum,
    Graph
  },
  data () {
    return {
      msg: 'Calculate money  😞😤',
      list: [],
      entries: [
        {
          counting: 1000,
          created_at: '2018-06-21'
        }
      ]
    }
  },
  methods: {
    onEnlargeText (form) {
      if (form.text && (parseFloat(form.money) > 0)) {
        this.list.push(form)
      }
    },
    saveMoney (money) {
      this.entries.push({ counting: money, created_at: this.dayjs().format('YYYY-MM-DD') })
      console.log(this.entries)
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
