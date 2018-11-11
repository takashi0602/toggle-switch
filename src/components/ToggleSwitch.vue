<template>
  <div id="app">
    <div class="switch">
      <label class="switch__label">
        <input type="checkbox" :class="{'switch__input': true, 'switch__checked': checked}" v-model="checked"/>
        <span class="switch__content"></span>
        <span class="switch__circle"></span>
      </label>
      <span class="switch__text">{{ display() }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'toggle-switch',
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
.switch {
  &__label {
    width: 37px;
    position: relative;
    display: inline-block;
    padding-top: 3px;
  }
  &__input {
    display: none;
  }
  &__content {
    display: block;
    position: relative;
    border-radius: 7px;
    height: 14px;
    background-color: #e0e0e0;
    transition: all .5s;
    &:after {
      content: "";
      display: block;
      position: absolute;
      width: 0;
      height: 100%;
      top: 0;
      left: 0;
      border-radius: 7px;
      transition: all .5s;
    }
  }
  &__circle {
    cursor: pointer;
    display: block;
    top: 0px;
    left: 0px;
    position: absolute;
    width: 20px;
    height: 20px;
    border-radius: 50%;
    background-color: #F1F1F1;
    transition: all .5s;
    box-shadow: 0 2px 2px #ccc;
  }
  &__checked ~ &__circle {
    left: 18px;
    background-color: #009688;
  }
  &__checked ~ &__content {
    border-color: transparent;
    transition: all 0s;
  }

  &__checked ~ &__content:after {
    background-color: #009688;
    opacity: 0.5;
    width: 100%;
  }
  &__text {
    margin-left: 10px;
  }
}
</style>
