<template>
  <div>
    <md-card class="card-container" md-with-hover>
      <md-ripple>
        <md-card-header>
          <div class="md-title">{{this.$props.bundle.title}}</div>
          <div class="md-subhead">{{this.$props.bundle.subTitle}}</div>
        </md-card-header>

        <md-card-content>
          {{this.$props.bundle.description}}
        </md-card-content>
      </md-ripple>
    </md-card>
  </div>
</template>
<script>
export default {
  name: 'Item',
  props: {
    bundle: Object
  },
  data () {
    return {

    }
  }
}
</script>
<style scoped>
.card-container{
  width: 200px;
  height: 250px;
  margin: 0 0 0 0;
}
</style>
