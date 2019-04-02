<template>
  <div>
    <md-dialog :md-active.sync="this.toShowData">
      <md-dialog-title>LoveTo</md-dialog-title>
      <md-dialog-actions>
        <md-button class="md-primary" @click="onClosed">Close</md-button>
      </md-dialog-actions>
    </md-dialog>
  </div>
</template>
<script>
export default {
  Name: 'LoveTo',
  props: {
    toShow: Boolean
  },
  watch: {
    toShow: function (newVal, oldVal) {
      let vm = this
      if (newVal) vm.toShowData = newVal
    }
  },
  data () {
    return {
      toShowData: false
    }
  },
  methods: {
    onClosed: function () {
      this.toShowData = false
      this.$emit('viewClicked', {toShow: false, title: 'LoveTo'})
    }
  },
  mounted () {
    var vm = this
    if (vm.$props.toShow) vm.toShowData = vm.$props.toShow
  }
}
</script>
