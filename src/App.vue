<template>
  <div id="app">
    <toggle-switch />
  </div>
</template>

<script>
import ToggleSwitch from "./components/ToggleSwitch";

export default {
  components: {ToggleSwitch},
  name: 'app',
  component : {
    ToggleSwitch
  },
  data: function () {
    return {
      msg: [
        '表示する',
        '表示しない'
      ],
      checked : true,
    }
  },
  methods: {
    display: function() {
      if(this.checked) {
        return this.msg[0];
      }else{
        return this.msg[1];
      }
    }
  }
}
</script>

<style lang="scss">

</style>
