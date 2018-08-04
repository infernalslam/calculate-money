<template>
  <div>
    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <ul>
          <li v-for="(l, index) in list" :key="index">
            <span class="is-size-3" @dblclick="edit(index)" v-if="index !== editIndex"> {{ l.text }} </span>
            <span class="is-size-3">{{ l.money }}</span>
            <div>
              <input type="text" v-model="l.text" v-if="index === editIndex" @blur="blurFunction(l)" @keyup.enter="blurFunction(l)">
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['list'],
  data () {
    return {
      editIndex: -1
    }
  },
  methods: {
    edit (index) {
      this.editIndex = index
    },
    blurFunction (data) {
      if (data) {
        this.editIndex = -1
      }
    }
  }
}
</script>
