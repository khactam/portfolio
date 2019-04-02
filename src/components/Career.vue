<template>
  <div>
    <md-dialog :md-active.sync="this.toShowData">
      <md-dialog-title>My 'always panic' path but I love it.</md-dialog-title>
      <md-button @click="onClosed" class="button-fixed md-icon-button">
        <md-icon>close</md-icon>
      </md-button>
      <md-content>
        <Timeline
          :timeline-items="dataTimeline"
          :message-when-no-items="messageWhenNoItems"
        />
      </md-content>
    </md-dialog>
  </div>
</template>
<script>
import Timeline from './Timeline.vue'

export default {
  Name: 'Career',
  props: {
    toShow: Boolean
  },
  components: {Timeline},
  watch: {
    toShow: function (newVal, oldVal) {
      let vm = this
      if (newVal) vm.toShowData = newVal
    }
  },
  data () {
    return {
      toShowData: true,
      messageWhenNoItems: 'No articles found.',
      dataTimeline: [
        {
          from: new Date(2019, 1),
          title: 'Co-Founder: Viet\'s Kitchen Oy (current), Lahti, Finland.',
          description:
          'Tasting good food is aways a nice thing to do in life to me (to you too). I travelled countries, cities and towns to learn new cultures and taste good food. Creating good food is basically the best job on Earth. Viet\'s Kitchen was born for my love of food.'
        },
        {
          from: new Date(2018, 11),
          title: 'Founder - CEO: OriginSyntax Oy (current), Lahti, Finland.',
          description:
          'My passion is to create something I want with newest technology where big companies are scared of, that is the reason I created OriginSyntax Oy, to just do software that I like (and will occationally sell it). I have a few trainees to help me build stuff. This is my playground (sometimes I make money from it too).'
        },
        {
          from: new Date(2017, 2),
          title: 'Software developer: SuperApp Oy (current), Lahti, Finland.',
          description:
          'Being as a software developer, I have found myself patience which is not my ability ever before. I love playing with numbers but not with chars and integers but lately I found them interesting somehow. Working on many projects and products and are live on AppStore and PlayStore (and a few websites that I do not anyone to find out).'
        },
        {
          from: new Date(2016, 8),
          title: 'Freetime investor (current)',
          description:
          'Chasing dreams to be a cool and rich kid ended when I was 15yo. Now I\'m chasing the dream to be a cool and rich middle age gentlement by investing small money and praise for it. Seriously, I\'m not making really good money in investing but it\'s interesting.'
        },
        {
          from: new Date(2016, 8),
          title: 'Developer trainee: SuperApp Oy (5 months), Lahti, Finland.',
          description:
          'Good time for me to train. Do all kind of stuff that nobody wants to do and usually hard and new stuff. Love the time when I feel I could do everything and free of stress. The good old days.'
        },
        {
          from: new Date(2015, 5),
          title: 'Warehouse goods supervisor: HKScan Oy (8 months), Vanta, Finland.',
          description:
          'Supervise goods and products in warehouse was a hardcore job every night. The warehouse was big and I was and am small even tiny. However, that made me feel so nice and comfortable every paycheck, student needed money.'
        }
      ]
    }
  },
  methods: {
    onClosed: function () {
      this.toShowData = false
      this.$emit('viewClicked', {toShow: false, title: 'Career'})
    }
  },
  mounted () {
    var vm = this
    if (vm.$props.toShow) vm.toShowData = vm.$props.toShow
  }
}
</script>
<style scoped>
.md-dialog {
  width: 80vw;
  max-width: none;
  height: 90vh;
  overflow-y: scroll;
  border-radius: 20px;
}
.button-fixed{
  position: absolute;
  top: 10px;
  right: 10px;
}
.md-ripple{
  overflow: visible;
}
</style>
