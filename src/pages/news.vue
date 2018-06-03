<template>
<div class="body">
 <div class="page-body">
  <div class="page-header">
    <el-select class="select1" v-model="value" placeholder="发布状态" >
    <el-option 
      v-for="item in options"
      :key="item.value"
      :label="item.label"
      :value="item.value">
    </el-option>
  </el-select>
  	
  	<el-select class="select1"  v-model="value1" placeholder="发布来源">
    <el-option
      v-for="item in optionss"
      :key="item.value1"
      :label="item.label"
      :value="item.value1">
    </el-option>
  </el-select>
  
	<el-select class="select1" v-model="value2" placeholder="时间类型">
    <el-option
      v-for="item in optionsss"
      :key="item.value2"
      :label="item.label"
      :value="item.value2">
    </el-option>
  </el-select>
    <el-date-picker class="times"
      v-model="value6"
      type="datetimerange"
      start-placeholder="开始日期"
      end-placeholder="结束日期"
      :default-time="['12:00:00']">
    </el-date-picker>
    <el-input class="inputs" v-model="inputs" placeholder="标题、发布账号、文章ID"></el-input><el-button class="light_btn">搜素</el-button>
    
    <div style="margin-top: 15px;text-align: right;">
      <router-link :to="{name:'news-add'}" ><el-button size="small" class="light_btn">添加新闻</el-button></router-link>
    	<el-button size="small" class="light_btn">发布置顶</el-button>
    	<el-button size="small" class="light_btn">刷新</el-button>
    	
    </div>
  </div>

  <div class="box">
    <el-table :data="tableData">
      <!--<el-table-column label="#" type="index"></el-table-column>-->
      <el-table-column label="序号" prop="id"></el-table-column>
      <el-table-column label="标题" prop="action"></el-table-column>
      <el-table-column label="创建人" prop="result"></el-table-column>
      <el-table-column label="发布状态" prop="desctiption"></el-table-column>
      <el-table-column label="发布来源" prop="show" ></el-table-column>
      <el-table-column label="文章ID" prop="cont" ></el-table-column>
      <el-table-column label="操作">
        <template slot-scope="scope">
          <el-button icon="el-icon-search" circle></el-button>
          <el-button type="primary" icon="el-icon-edit" circle></el-button>
          <el-button type="success" icon="el-icon-check" circle></el-button>
          <el-button type="info" icon="el-icon-message" circle></el-button>
          <el-button type="warning" icon="el-icon-star-off" circle></el-button>
          <el-button type="danger" icon="el-icon-delete" circle></el-button>
        </template>
      </el-table-column>
    </el-table>
   
    </div>
 </div>
</div>
</template>
<script type="text/javascript">
export default {
  name: 'home',
    data() {
      return {
        tableData: [{
            id: '2016-05-02',
            action: '王小虎',
            result: '上海市普陀区金沙江路 1518 弄',
            desctiption:'222222',
            show:'hahha',
            cont:'123'
          },
          {
            id: 'eeeeeee',
            action: '哎呀呀呀晕晕晕晕',
            result: '这是是是是是',
            desctiption:'口水了，索尼',
            show:'昙花一现',
            cont:'良辰美景'
          }],
        options: [{
          value: '选项1',
          label: '全部'
        }, {
          value: '选项2',
          label: '待提交审核'
        }, {
          value: '选项3',
          label: '待审核'
        }, {
          value: '选项4',
          label: '审核不通过'
        }, {
          value: '选项5',
          label: '已上线'
        }, {
          value: '选项6',
          label: '已下线'
        }],
         optionss: [{
          value1: '选项1',
          label: '全部'
        }, {
          value1: '选项2',
          label: 'APP'
        }, {
          value1: '选项3',
          label: '后台发布'
        }, {
          value1: '选项4',
          label: '数据爬取'
        }],
          optionsss: [{
          value2: '选项1',
          label: '上线时间'
        }, {
          value2: '选项2',
          label: '创建时间'
        }, {
          value2: '选项3',
          label: '下线时间'
        }, {
          value2: '选项4',
          label: '审核时间'
        }],
        value6: '',
        inputs: '',
        value: '',
        value1:'',
        value2:'',
        dataList:[],
      }
    }
  }
</script>
<style type="text/css">
  .test{
    height: 40px;
    background: #EBEFF4;
    margin-bottom: 15px;
  }
  .inputs{
  	width: 15%;
  }
  .select1{
  	width: 10% !important;
  	margin-right: 10px;
  }
  .times{
  	width: 30% !important;
  	margin-right: 30px;
  }
  /*.el-input__inner{
  	height: 30px;
  }*/
</style>