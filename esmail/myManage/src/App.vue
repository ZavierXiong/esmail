<template>
  <div id="app">
    <header>
      <ul>
        <li class="logo"></li>
        <li><i></i>工作台</li>
        <li><i></i>搜客户</li>
        <li><i></i>邮件</li>
        <li><i></i>营销</li>
        <li><i></i>客户</li>
        <li><i></i>数据</li>
        <li><i></i>团队</li>
      </ul>
      <ul class="user-operater">
        <li>1</li>
        <li>2</li>
        <li>3</li>
        <li>4</li>
      </ul>
    </header>
    <div class="left-tab">
      <div class="product-name"><i></i><span>客户管理系统(CRM)</span></div>
      <ul class="user-list">
        <li><i></i><span>新建客户</span></li>
        <li>公海客户<span class="red-num">(240)</span></li>
        <li>客户回收站<span class="red-num">(6)</span></li>
      </ul>
      <el-tree :data="data" :props="defaultProps" @node-click="handleNodeClick" class="tab-list"></el-tree>
      <ul class="client-origin">
        <li>我的客户状态<span>(7)</span></li>
        <li>同事共享给我的<span>(0)</span></li>
        <li>已入客户库联系人<span>(17)</span></li>
        <li>未入客户库联系人<span>(3)</span></li>
      </ul>
    </div>
    <div class="tab-content">
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import Element from 'element-ui'
import 'element-ui/lib/theme-default/index.css'

Vue.use(Element)

export default {
  name: 'app',
  data() {
    return{
      data: [
        {
          label: '全部客户',
          children: [{
            label: '重点跟进客户',
          },{
            label: '默认分类',
          },{
            label: '重点意向客户',
          },{
            label: '一般潜在客户',
          },{
            label: '阿里',
          },{
            label: '美国客户',
          },{
            label: 'JP',
          },{
            label: 'KP',
          }]
        },
        {
          label: '客户状态',
          children: [{
            label: '收集状态',
          },{
            label: '开发状态',
          },{
            label: '跟进状态',
          },{
            label: '潜在客户',
          },{
            label: '意向客户',
          },{
            label: '成交客户',
          }]
        }
      ],
      defaultProps: {
        children: 'children',
        label: 'label'
      }
    };
  },
  methods:{
    handleNodeClick(data) {
      console.log(data);
    }
  }
};
</script>

<style>
body{
  margin:0;
}
ul{
  padding:0;
  margin:0;
  list-style:none;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.logo{
  width:159px;
  height:55px;
  background: url(./assets/logo.png) 50% 50% no-repeat;
  border-left:0;
}
.logo:hover{
  cursor:default;
  background-color:#1965b6;
}
header{
  min-width:1920px;
  max-width:100%;
  height:55px;
  line-height:55px;
  background-color:#1965b6;
  font-size:16px;
}
  header>ul{
    overflow:auto;
    padding:0;
    float:left;
  }
  header>ul>li{
    cursor:pointer;
    float:left;
    padding:0 20px;
    color:#fff;
    border-left:1px solid #3075bd;
  }
  header>ul>li:hover{
    background-color:#0b559f;
  }
  .user-operater{
    float:right;
  }
  .left-tab{
    position:absolute;
    top:55px;
    bottom:0;
    left:0;
    width:200px;
    border-left:1px solid #ddd;
    border-right:1px solid #ddd;
    background-color:#FCFCFC;
  }
  .product-name{
    height:40px;
    line-height:40px;
    font-size:14px;
    color:#1562b4;
    background-color:#e6e6e6;
    padding:0 20px;
  }
  .product-name>i{
    float: left;
    width: 22px;
    margin-top: 8px;
    height: 25px;
    background: url(./assets/icon.png) no-repeat 0px 2px;
  }
  .user-list>li{
    background-color:#0480be;
    color:#fff;
    margin-top:10px;
    height:30px;
    line-height: 30px;
    text-align:center;
    font-size:14px;
  }
  .user-list .red-num{
    color:red;
  }
  .el-tree-node__label{
    font-size:12px;
  }
  .tab-list{
    margin-top:10px;
    border-right:0;
    border-left:0;
    background-color:#FCFCFC;
  }
  .tab-list>.el-tree-node{
    margin-top:10px;
  }
  .tab-list .el-tree-node .el-tree-node__content{
    height:28px;
    line-height: 28px;
    text-align:left;
    padding-left:30px!important;
  }
  .tab-list .el-tree-node .el-tree-node__content:hover{
    background-color:#0480be;
    color:#fff;
  }
  .tab-list .el-tree-node__children .el-tree-node__content{
    text-indent:5px;
  }
  .left-tab .client-origin{
    box-sizing:border-box;
    border-bottom:1px solid #ddd;
  }
  .left-tab .client-origin>li{
    font-size:12px;
    height:30px;
    line-height: 30px;
    text-align:left;
    padding-left:30px;

  }
  .left-tab .client-origin>li>span{
    color:red;
  }
</style>
