<template>
  <div>
  <div class="vux-1px-t">

    <swipeout>

      <swipeout-item transition-mode="follow">
        <div slot="right-menu">
          <swipeout-button @click.native="onButtonClick('fav')" type="primary" :class='state === 1 ? "disabled":""' :disabled ='state === 2 ? true:false'>'Yes'</swipeout-button>
          <swipeout-button @click.native="onButtonClick('delete')" type="warn">'Right'</swipeout-button>
        </div>
        <div slot="content" class="demo-content vux-1px-t" >
        {{`${'JavaScript is the best language'.substr(0,30)}...`}}
        </div>
      </swipeout-item>



    </swipeout>
  </div>



    <br>
    <br>
  </div>
</template>

<i18n>
Fav:
  zh-CN: 收藏
Delete:
  zh-CN: 删除
JavaScript is the best language:
  zh-CN: JavaScript 是最好的语言
now enabled:
  zh-CN: 当前可操作
now disabled:
  zh-CN: 当前不可操作
set Enabled:
  zh-CN: 设置可操作
set Disabled:
  zh-CN: 设置不可操作
open left menu:
  zh-CN: 打开左菜单
open right menu:
  zh-CN: 打开右菜单
close menu:
  zh-CN: 关闭菜单
threshold = 0.5:
  zh-CN: 设置滑动阙值为 0.5
Yes:
  zh-CN: 是的
Right:
  zh-CN: 正确
Ignore:
  zh-CN: 忽略
</i18n>

<script>
import { GroupTitle, Swipeout, SwipeoutItem, SwipeoutButton, XButton, Toast } from 'vux'
export default {
  components: {
    GroupTitle,
    Swipeout,
    SwipeoutItem,
    SwipeoutButton,
    XButton,
    Toast
  },
  methods: {
    onButtonClick (type) {
      alert('on button click ' + type)
    },
    handleEvents (type) {
      console.log('event: ', type)
    }
  },
  data () {
    return {
      disabled: false,
      state: 2
    }
  },
  mounted () {
    this.$vux.toast.show({
      text: 'Loading'
    })
  }
}
</script>

<style lang="less">
.demo-content {
  padding: 10px 10px;
}

div button.disabled{
border:1px solid #DDD;
background-color:#F5F5F5;
color:#ACA899;
}
</style>
