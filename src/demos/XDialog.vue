<template>
  <div style="height: 1000px">
    <group>
      <x-switch v-model="show" title="Toggle"></x-switch>
      <x-switch v-model="showHideOnBlur" title="点击遮罩自动关闭"></x-switch>
    </group>
    <group style="padding-top: 300px">
      <x-switch v-model="showNoScroll" title="背景不可滚动"></x-switch>
    </group>
    <div v-transfer-dom>
      <x-dialog v-model="show" class="dialog-demo">
        <p class="dialog-title">I'm a bg scroll Dialog.</p>
        <div class="img-box">
          <img src="../assets/demo/dialog/01.jpg" style="max-width:100%">
        </div>
        <span class="vux-close" @click="show=false"></span>
      </x-dialog>
    </div>
    <div v-transfer-dom>
      <x-dialog v-model="showHideOnBlur" class="dialog-demo" :hideOnBlur="true">
        <p class="dialog-title">I'm a bg scroll Dialog.</p>
        <div class="img-box">
          <img src="../assets/demo/dialog/01.jpg" style="max-width:100%">
        </div>
        <span class="vux-close" @click="showHideOnBlur=false"></span>
      </x-dialog>
    </div>
    <div v-transfer-dom>
      <x-dialog v-model="showNoScroll" class="dialog-demo" :scroll="false">
        <p class="dialog-title">I'm a no scroll Dialog.</p>
        <div class="img-box">
          <img src="../assets/demo/dialog/01.jpg" style="max-width:100%">
        </div>
        <span class="vux-close" @click="showNoScroll=false"></span>
      </x-dialog>
    </div>

    <group style="padding-top: 300px">
      <x-switch v-model="showScrollBox" title="主体内容滚动"></x-switch>
    </group>
    <div v-transfer-dom>
      <x-dialog v-model="showScrollBox" class="dialog-demo">
        <p class="dialog-title">Long content</p>
        <div class="img-box" style="height:100px;padding:15px 0;overflow:scroll;-webkit-overflow-scrolling:touch;">
          <p v-for="i in 20">{{i}}</p>
        </div>
        <span class="vux-close" @click="showScrollBox=false"></span>
      </x-dialog>
    </div>

  </div>
</template>

<script>
import { XDialog, XButton, Group, XSwitch, TransferDomDirective as TransferDom } from 'vux'

export default {
  directives: {
    TransferDom
  },
  components: {
    XDialog,
    XButton,
    Group,
    XSwitch
  },
  data () {
    return {
      show: false,
      showNoScroll: false,
      showHideOnBlur: false,
      showScrollBox: false
    }
  }
}
</script>

<style lang="less" scoped>
@import '~vux/src/styles/close';
.dialog-demo {
  .weui-dialog{
    border-radius: 8px;
    padding-bottom: 8px;
  }
  .dialog-title {
    line-height: 30px;
    color: #666;
  }
  .img-box {
    height: 350px;
    overflow: hidden;
  }
  .vux-close {
    margin-top: 8px;
    margin-bottom: 8px;
  }
}
</style>
