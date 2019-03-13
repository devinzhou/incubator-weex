<template>
  <div>
    <div>
      <text style="font-size: 100px;" @click="textClick">Hello World.2</text>
    </div>
    <div>
      <wxbutton size="middle" value="测试" @click="btnClick($event)"></wxbutton>
    </div>
  </div>
</template>

<script>
  import WxButton from './include/button.vue'

  let modal = weex.requireModule("modal");

  export default {
    data: function () {
      return {

      }
    },
    beforeCreate: function() {
      console.log('hello world beforeCreate')
    },

    mounted: function () {
      console.log('hello world mounted')
    },
    components: {
      wxbutton: require('./include/button.vue')
    },
    methods: {
      textClick: function () {
        modal.alert({
          message: 'test alert',
          duration: 3
        })
      },

      btnClick: function () {
        let arg = arguments;
        modal.alert({
          message: 'test btn : ' + arg[0].type,
          duration: 2
        })
      }
    }
  }

</script>