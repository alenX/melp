<template>

  <div>
    <br>
    <x-header>Melp</x-header>
    <br>
    <group title="发布信息">
      <x-input title="姓名" placeholder="输入姓名" v-model="name"></x-input>
      <x-input title="电话" placeholder="输入手机号" v-model="tel"></x-input>
      <datetime v-model="startDate" format="YYYY-MM-DD HH:mm"
                :minute-list="['00', '15', '30', '45']" @on-change="change" title="起始时间"></datetime>
      <datetime v-model="endDate" format="YYYY-MM-DD HH:mm"
                :minute-list="['00', '15', '30', '45']" @on-change="change" title="失效时间"></datetime>

      <x-textarea title="消息内容" v-model="info" :max=30  placeholder="发布消息内容"></x-textarea>

      <flexbox>
        <flexbox-item>
          <x-button type="primary" @click.native="sendInfo">发布</x-button>
        </flexbox-item>
        <flexbox-item>
          <x-button type="warn" @click.native="resetInfo">重置</x-button>
        </flexbox-item>
      </flexbox>
      <toast v-model="showPositionValue" type="text"
             :time="800" is-show-mask text="发布成功" position="middle">发布成功1</toast>
    </group>
  </div>
</template>

<script>
  import {XInput, Group, Datetime, XTextarea, XButton, Flexbox, FlexboxItem, Toast, XHeader} from 'vux'

  export default {
    name: 'SendInfo',
    components: {XInput, Group, Datetime, XTextarea, XButton, Flexbox, FlexboxItem, Toast, XHeader},
    data () {
      return {
        name: '',
        tel: '',
        startDate: '',
        endDate: '',
        info: '',
        length: 30,
        showPositionValue: false
      }
    },
    methods: {
      change: function () {
      },
      resetInfo: function () {
        this.info = ''
      },
      sendInfo: function () {
        this.showPositionValue = true
        /*this.$vux.toast.show({
          text: '发布成功2',
          onShow () {
            console.log('Plugin: I\'m showing')
          },
          onHide () {
            console.log('Plugin: I\'m hiding')
          }
        })*/
      }
    }
  }
</script>

<style scoped>

</style>
