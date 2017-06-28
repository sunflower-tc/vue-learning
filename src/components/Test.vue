<template>
  <div class="test">
  <!-- html -->
  {{message}}
  <!-- 属性 -->
  <label for="name">姓名</label>
  <!-- 绑定class属性 -->
  <input id="name" type="checkbox" v-model="class1" v-bind:class="{'class1': class1}" /><br>
  <!--表达式  -->
  {{5+5}} {{'ok'?'YES':"NO"}}<br>
  {{ message.split('').reverse().join('') }}
  <div v-bind:class="'list_'+ people">sunflower</div>
  <!-- 指令 -->
  <div v-if="show">显示隐藏</div>
  <!--  参数-->
  <a v-bind:href="url">点我到百度</a>
  <div class="" v-on:click="clickMe">点我</div>
  <!--修饰符是以半角句号 . 指明的特殊后缀，用于指出一个指定应该以特殊方式绑定。
  例如，.prevent 修饰符告诉 v-on 指令对于触发的事件调用 event.preventDefault()：  -->
  <form v-on:submit.prevent="submit">onSubmit</form>
  <!-- 用户输入 -->
  <div class="">{{value}}</div>
  <input type="text" name=""  v-model="value">
    <!--点击事件字符串反转  -->
    <p>{{reseradc}}</p>
    <button type="button" name="button" v-on:click="reserClick">点我反转</button> <br>
    <!--过滤器  可以串联  -->
    {{filter | capitalizes}}<br>
    {{ filter | filterA | filterB }}
    <!-- {{ message | filterA('arg1', arg2) }}
      这里，message 是第一个参数，字符串 'arg1' 将传给过滤器作为第二个参数， arg2 表达式的值将被求值然后传给过滤器作为第三个参数。
     -->

    <!--  -->
    <!--  -->
    <!--  -->
    <!--  -->
    <!--  -->
    <!--  -->

  </div>
</template>

<script>
export default {
  name:'test',
  data(){
    return {
      message:"learning vue",
      class1:true,
      ok:true,
      people:"people",
      show:false,
      url:'https://www.baidu.com/?tn=62095104_oem_dg',
      value:'test----input',
      reseradc:"ABCD",
      filter:'my name is tan chang'
    }
  },
  methods:{
    clickMe:function(){
      alert("click");
    },
    reserClick:function(){
      this.reseradc = this.reseradc.split('').reverse().join('')
    }
  },
  filters:{
    capitalizes: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1)
    },
    filterA:function(val){
      return val+"filterA"
    },
    filterB:function(val){
      return " "+val+"filterB"
    }
  },
}
</script>

<style lang="css">
</style>
