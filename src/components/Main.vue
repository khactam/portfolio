<template>
  <div class="cards-container">
    <div class="card-container" v-for="(bundle, index) in this.bundles" :key="index">
      <item :bundle="bundle" @click.native="itemOnClick(bundle)"></item>
    </div>
    <education :toShow="this.bundles[0].toShow" @viewClicked="onViewClicked"></education>
    <career :toShow="this.bundles[1].toShow" @viewClicked="onViewClicked"></career>
    <good-at :toShow="this.bundles[2].toShow" @viewClicked="onViewClicked"></good-at>
    <love-to :toShow="this.bundles[3].toShow" @viewClicked="onViewClicked"></love-to>
  </div>
</template>
<script>
import Item from './Item.vue'
import Education from './Education.vue'
import Career from './Career.vue'
import GoodAt from './GoodAt.vue'
import LoveTo from './LoveTo.vue'
export default {
  name: 'Main',
  components: {Education, Item, Career, GoodAt, LoveTo},
  data () {
    return {
      bundles: [
        {
          title: 'Education',
          subTitle: 'Wonder schools.',
          description: 'Education is the most important part of my life. Know how to Math and love Physics. Used to good at Chemistry and never understand Biology.',
          toShow: false
        },
        {
          title: 'Career',
          subTitle: 'Panic path.',
          description: 'I did not choose the programming life, the programming life chose me. Also being an entrepreneur so life is as coffee and milk.',
          toShow: false
        },
        {
          title: 'GoodAt',
          subTitle: 'Things I know how.',
          description: 'Skill set that I know, languages that I speak, also include a few things I randomly put to attract headhunters.',
          toShow: false
        },
        {
          title: 'LoveTo',
          subTitle: 'Stuff I love',
          description: 'Things I like to do everyday, just like another guy saying what he loves to do to attract headhunters, but I do love them.',
          toShow: false
        }
      ]
    }
  },
  mounted () {
  },
  methods: {
    itemOnClick: function (item) {
      item.toShow = !(item.toShow)
    },
    onViewClicked: function (data) {
      let bundle = this.bundles.find(bundle => bundle.title === data.title)
      bundle.toShow = data.toShow
    }
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
