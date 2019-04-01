<template>
  <div class="cards-container">
    <div class="card-container" v-for="(bundle, index) in this.bundles" :key="index">
      <item :bundle="bundle"></item>
    </div>

  </div>
</template>
<script>
import Item from './Item.vue'
export default {
  name: 'Main',
  components: {Item},
  data () {
    return {
      bundles: [
        {
          title: 'Education',
          subTitle: 'Wonder schools.',
          description: 'Education is the most important part of my life. Know how to Math and love Physics. Used to good at Chemistry and never understand Biology.'
        },
        {
          title: 'Career',
          subTitle: 'Panic path.',
          description: 'I did not choose the programming life, the programming life chose me. Also being an entrepreneur so life is as coffee and milk.'
        },
        {
          title: 'GoodAt',
          subTitle: 'Things I know how.',
          description: 'Skill set that I know, languages that I speak, also include a few things I randomly put to attract headhunters.'
        },
        {
          title: 'LoveTo',
          subTitle: 'Stuff I love',
          description: 'Things I like to do everyday, just like another guy saying what he loves to do to attract headhunters, but I do love them.'
        }
      ]
    }
  },
  mounted () {
    console.log(this.bundles)
  }
}
</script>
<style scoped>
.cards-container{
  width: 450px;
  text-align: center;
  margin: auto;
}
.card-container{
  display: inline-block;
  margin-left: 5px;
  margin-right: 5px;
}
</style>
