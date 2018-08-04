<template>
  <div>
    <div class="columns">
      <div class="column is-half is-offset-one-quarter">
        <div class="columns" v-for="(l, index) in list" :key="index">
          <div class="column has-text-left">
            <div  class="is-size-3" @dblclick="edit(index, 'text')" v-show="index !== editIndex || editType === 'money'"> {{ l.text }} </div>
            <div class="is-size-3" v-show="index === editIndex && editType === 'text' " >
              <input type="text" v-model="l.text"  @blur="blurFunction(l)" @keyup.enter="blurFunction(l)">
            </div>
          </div>
           <div class="column has-text-right">
             <div  class="is-size-3" @dblclick="edit(index, 'money')" v-show="index !== editIndex || editType === 'text'"> {{ l.money }}</div>
             <div class="is-size-3" v-show="index === editIndex && editType === 'money' " >
              <input type="text" v-model="l.money"  @blur="blurFunction(l)" @keyup.enter="blurFunction(l)">
            </div>
           </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['list'],
  data () {
    return {
      editIndex: -1,
      editType: ''
    }
  },
  methods: {
    edit (index, type) {
      if (type === 'text') {
        this.editType = 'text'
      } else {
        this.editType = 'money'
      }
      this.editIndex = index
    },
    blurFunction (data) {
      if (data) {
        this.editIndex = -1
        this.editType = ''
      }
    }
  }
}
</script>

<style>
.flex {
  display: flex;
  justify-content: space-between;
}
</style>
