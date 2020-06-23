<template>
  <div class="invatation">
    <div class="form">
      <div class="item" @click="goNav('../detail/main')">
        <label class="label">小区名称</label>
        <p class="inpt">{{xiaoqu}}</p>
        
      </div>
      <div class="item">
        <label class="label">钥匙名称</label>
        <p class="inpt">{{xiaoqu}}</p>
        <span></span>
      </div>
      <div class="item">
        <label class="label">来访时间</label>
        <p class="inpt">{{other}}</p>
      </div>
      <div class="item">
        <label class="label"></label>
        <p class="inpt">结束时间</p>
      </div>
      <div class="item">
        <label class="label">访客手机</label>
        <input class="inpt" type="text" placeholder="请输入手机号码" placeholder-style="color: #9EA6B7;">
      </div>
    </div>
  </div>
</template>
<script>
let that = null;
export default {
  data() {
    return {
      xiaoqu: "请选择小区",
      other: 'kkk',
      setData: function (key,value) {
        that[key] = value
      }
    }
  },
  mounted () {
   that = this;
},
  methods:{
    goNav(url){
      this.other = " nihao"
      mpvue.navigateTo({ url })
    }
  }
}
</script>
<style>
.invatation {
}
.form .item{
  display: flex;
  padding: 15px 20px;
}
.form .item:not(:first-child){
  border-top: 1px solid #F4F6F8;
}
.form .label{
  width: 85px;
  font-size: 15px;
  line-height: 21px;
}
.form .icon{
  flex: 1;
  text-align: right;
}
.inpt {
  font-size: 14px;
  line-height: 20px;
  color: #9EA6B7;
}
</style>