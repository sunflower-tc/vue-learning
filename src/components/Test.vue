<template>
  <div class="test">
    <div class="" style="float:left">
      <h2>模板语法</h2>
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
  </div>
  <div class="" style="float:left">
    <!--条件判断  -->
   <h2>条件判断</h2>
     <!-- v-if -->
    <p v-if="see">看见</p>
    <template v-if="ok">
      <h4>菜鸟教程</h4>
      <p>学的不仅是技术，更是梦想！</p>
    </template>
    <!-- v-else -->
    <div class="" v-if="Math.random() > 0.5">
       <p>显示</p>
    </div>
    <div class="" v-else>
      <p>不显示</p>
    </div>
    <!-- v-else-if  -->
    <div v-if="type === 'A'">  A </div>
    <div v-else-if="type === 'B'">  B </div>
    <div v-else-if="type === 'C'">  C </div>
    <div v-else> Not A/B/C</div>
    <!-- v-show  -->
    <div class="" v-show="ok">显示v-show</div>
  </div>
  <div class="" style="float:left">
     <h2>循环语句</h2>
      <p>v-for:  item in items 形式</p>
      <ul>
        <li v-for="student in students">{{student.name}}</li>
      </ul>
      <p>v-for:val in object</p>
      <ul>
        <li v-for="val in object">{{val}}</li>
      </ul>
      <p>v-for：(value, key,index) in object </p>
      <ul>
        <li v-for="(val,key,index) in object">{{index}}:{{key}}:{{val}}</li>
      </ul>
      <p>v-for 循环整数</p>
      <ul>
        <li v-for="n in 2">{{n}}</li>
      </ul>
  </div>
  <div class="" style="float:left">
    <h2>vue计算属性</h2>
    <p>计算属性： computed</p>
    <p> computed vs methods</p>
    <div class="">{{message}}</div>
    <input type="text" name=""   v-model="message">
    <div class="">使用计算属性{{reversedMessage}}</div>
    <div class="">使用method方法{{reversedMessage2()}}</div>

    <!-- 我们可以使用 methods 来替代 computed，效果上两个都是一样的，但是 computed 是基于
    它的依赖缓存，只有相关依赖发生改变时才会重新取值。而使用 methods ，在重新渲染的时候，函数总会重新调用执行。 -->
    <p>computed setter</p>
    <!-- computed 属性默认只有 getter ，不过在需要时你也可以提供一个 setter ： -->
  </div>
  <div class="" style="float:left">
    <h2>vue样式绑定</h2>
    <p>v-bind:class 绑定类</p>
    <div class="static" v-bind:class="{active:isActive,waring:error}">active</div>
    <p>v-bind:class 绑定object类</p>
    <div class="" v-bind:class="classObject">object</div>
    <p>v-bind:class 绑定返回对象的计算属性</p>
    <div class="" v-bind:class="classObject2">计算属性</div>
    <p>v-bind:class 数组</p>
    <div class="" v-bind:class="[activeClass,staticClass]">数组</div>
    <p>v-bind:class 三元表达式</p>
    <div class="" v-bind:class="[isActive ? classObject :'']">数组</div>
    <p>v-bind:class 内连样式</p>
    <div class="" v-bind:style="{color:activeColor,fontSize:fontSize}">内联样式</div>
    <p>v-bind:class 内连样式对象</p>
    <div class="" v-bind:style="styleObject">My Name Is TC</div>
    <p>v-bind:class 内连样式数组</p>
    <div class="" v-bind:style="[baseStyles, overridingStyles]">My Name Is TC</div>

  </div>
  <div class="" style="float:left">
      <h2>vue事件处理器</h2>
      <p>v-on:指令</p>
      <div class="" v-on:click="couter+=1">增加1</div>
      <div>这个按钮被点击{{couter}}</div>
      <div class="" v-on:click="greet">点我打招呼</div>
      <p> 阻止单击事件冒泡 </p>
      <div class=""v-on:click="doParentThis"></div>
      <button v-on:click.stop="doThis">点我</button>
      <!-- 阻止单击事件冒泡 -->
      <a v-on:click.stop="doThis"></a>
      <!-- 提交事件不再重载页面 -->
      <form v-on:submit.prevent="onSubmit"></form>
      <!-- 修饰符可以串联  -->
      <a v-on:click.stop.prevent="doThat"></a>
      <!-- 只有修饰符 -->
      <form v-on:submit.prevent></form>
      <!-- 添加事件侦听器时使用事件捕获模式 -->
      <div v-on:click.capture="doThis">...</div>
      <!-- 只当事件在该元素本身（而不是子元素）触发时触发回调 -->
      <div v-on:click.self="doThat">...</div>

      <!-- click 事件至少触发一次，2.1.4版本新增 -->
      <a v-on:click.once="doThis"></a>
      <p>键盘修饰符</p>
      <input type="button" name="" value="enter回撤" v-on:keyup.enter="submit">
  </div>
   <div class="" style="float:left">
    <h2>vue表单</h2>
    <p>input元素</p>
    <input type="text" name="" value="" placeholder="请输入用户名" v-model="username">
    <div class="">{{username}}</div>
    <p>textarea元素</p>
    <textarea name="name" rows="8" cols="80" style="white-space:pre" v-model="textarea"></textarea>
    <p>{{textarea}}</p>
    <p>复选框</p>
    <input type="checkbox" id="checkbox" v-model="checked">
    <label for="checkbox">{{checked}}</label>
    <p>多个复选框</p>
    <input type="checkbox" id="runoob" value="Runoob" v-model="checkedNames">
    <label for="runoob">Runoob</label>
    <input type="checkbox" id="google" value="Google" v-model="checkedNames">
    <label for="google">Google</label>
    <input type="checkbox" id="taobao" value="Taobao" v-model="checkedNames">
    <label for="taobao">taobao</label>
   <br>
   <span>选择的值为: {{ checkedNames }}</span>
   <p>单选框</p>
   <input type="radio" name="" value="male" id="male" group="sex" v-model="sexValue">
   <label for="male">男</label>
   <input type="radio" name="" value="female" id="male" group="sex" v-model="sexValue">
   <label for="female">女</label>
   <br>
   <span>选择的值为: {{ sexValue }}</span>
   <p>select列表</p>
   <select class="" name="" v-model="selected" name="fruit">
      <option value="">请选择一个你喜欢的水果</option>
      <option value="banana">banana</option>
      <option value="apple">apple</option>
      <option value="orange">orange</option>
   </select>
   <span>你喜欢的水果是{{selected}}</span>
   <p>修饰符</p>
   <!-- 在 "change" 而不是 "input" 事件中更新 -->
   <input v-model.lazy="msg" >
   <input v-model.number="age" type="number">
   <input v-model.trim="msg">
   </div>
    <div class="" style="float:left">
      <h2>vue自定义组件</h2>
      <p>Vue.directive选项注册全局</p>
      <p>directives选项注册局部</p>
      <input type="text" name="" value="" v-focus>
      <p>钩子</p>
      
    </div>
  </div>
</template>

<script>
export default {
  name:'test',
  data(){
    return {
      msg:"",
      age:"",
      selected:'',
      sexValue:"",
      checked:false,
      checkedNames:[],
      couter:0,
      message:"learning vue",
      class1:true,
      ok:true,
      people:"people",
      show:false,
      url:'https://www.baidu.com/?tn=62095104_oem_dg',
      value:'test----input',
      reseradc:"ABCD",
      filter:'my name is tan chang',
      see:true,
      type:"N",
      index:'',
      zero:'',
      isActive:true,
      error:true,
      activeClass:"active",
      staticClass:"static",
      activeColor:"blue",
      fontSize:"20px",
      students:[
        {name:'HanMeiMei'},
        {name:'LiLei'},
        {name:'Lucy'},
      ],
      object:{
        name: 'TanChang',
        sex: 'female',
        age: '22'
      },
      classObject:{
        active:true,
        static:true
      },
      styleObject: {
      color: 'green',
      fontSize: '30px'
    },
    baseStyles: {
      color: 'green',
      fontSize: '30px'
    },
	overridingStyles: {
      'font-weight': 'bold'
    },
    username:"",
    textarea:""
    }
  },
  computed:{
    reversedMessage:function(){
      return this.message.split('').reverse().join('')
    },
    site:{
      get:function(){
        return this.people + ' ' + this.url
      },
      set:function (newValue) {
          var names = newValue.split(' ')
          this.people = names[0]
          this.url = names[names.length - 1]
        }
    },
    classObject2:function(){
      return {
        active: this.isActive && this.error,
        waring: this.error && this.error.type === 'fatal',
      }
    }
  },
  methods:{
    clickMe:function(){
      alert("click");
    },
    reserClick:function(){
      this.reseradc = this.reseradc.split('').reverse().join('')
    },
    reversedMessage2:function(){
      return this.message.split('').reverse().join('')
    },
    greet:function(){
      alert(this.couter);
    },
    doParentThis:function(){
      alert('parent');
    },
    doThis:function(){
     alert('child');
   },
   submit:function(){
     alert('enter')
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
  directives: {
   // 注册一个局部的自定义指令 v-focus
   focus: {
     // 指令的定义
     inserted: function (el) {
       // 聚焦元素
       el.focus()
     }
   }
 }
}

</script>

<style lang="css">
.static{
  font-size:18px;
  color:#fff;
}
.active{
  width:50px;
  height:50px;
  background: pink;
}
.waring{
  width:50px;
  height:50px;
  background: red;
}
</style>
