<template>
  <div>
    <text style="font-size: 100px;" @click="textClick">Hello World.2</text>
  </div>
</template>

<script>

  let modal = weex.requireModule("modal");

  export default {

    data: function () {
      return {

      }
    },

    mounted: function () {
      console.log('hello world mounted')
    },

    methods: {
      textClick: function () {
        modal.alert({
          message: 'test alert',
          duration: 3
        })
      }
    }
  }

</script>