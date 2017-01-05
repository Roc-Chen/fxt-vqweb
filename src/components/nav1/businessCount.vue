<template>
	<section>
		<!--工具条-->
		<el-col :span="24" class="toolbar">
			<el-form :inline="true" :model="formInline" class="demo-form-inline">
				<el-form-item label="日期："  label-width="60px">
					<el-date-picker v-model="value1" type="date" placeholder="选择日期" :picker-options="pickerOptions0" style="float: left;">
				    </el-date-picker>
				    <span style="text-align: center;line-height: 34px; float: left; margin:0 5px;">--</span>
				    <el-date-picker v-model="value2" type="date" placeholder="选择日期" :picker-options="pickerOptions1">
				    </el-date-picker>
				</el-form-item>
				<el-form-item label="客户名称：" label-width="90px">
				    <el-select placeholder="请选择客户名称">
				      <el-option label="全部" value="all"></el-option>
				      <el-option label="客户一" value="c1"></el-option>
				    </el-select>
				</el-form-item>
				<el-form-item label="业务类型：" label-width="90px">
				    <el-select placeholder="请选择业务类型">
				      <el-option label="全部" value="all"></el-option>
				      <el-option label="业务一" value="c1"></el-option>
				    </el-select>
				</el-form-item>
				<el-form-item>
					<el-button type="primary">查询</el-button>
				</el-form-item>
				<el-form-item>
					<el-button type="primary">导出列表</el-button>
				</el-form-item>
				<el-form-item>
					<el-button type="primary">周/月列表</el-button>
				</el-form-item>
			</el-form>
		</el-col>

		<!--列表-->
		<template>
			<el-table :data="tableData" highlight-current-row v-loading="listLoading" style="width: 100%;" border>
				<el-table-column prop="name" label="客户名称">
				</el-table-column>
				<el-table-column prop="type" label="业务类型">
				</el-table-column>
				<el-table-column prop="complate" label="完成量">
				</el-table-column>
				<el-table-column prop="avoidComplate" label="有效完成量" >
				</el-table-column>
				<el-table-column prop="totalComplate" label="当前累计完成量">
				</el-table-column>
			</el-table>
		</template>

		<!--分页-->
		<el-col :span="24" class="toolbar" style="padding-bottom:10px; padding-top: 15px">
			<el-pagination :current-page="1" :page-sizes="[100, 200, 300, 400]" :page-size="100" layout="total, sizes, prev, pager, next, jumper"
				:total="400" style="float:right">
			</el-pagination>
		</el-col>

	</section>
</template>

<script>
	import util from '../../common/util'
	import NProgress from 'nprogress'

  export default {
    data() {
      return {
      			pickerOptions0: {
		          disabledDate(time) {
		            return time.getTime() < Date.now() - 8.64e7;
		          }
		        },
		        pickerOptions1: {
		          disabledDate(time) {
		            return time.getTime() < Date.now() - 8.64e7;
		          }
		        },
				value1: '',
				value2: '',
				tableData: [{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				}, {
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				},{
					name: '平安普惠',
					type: '自动估价',
					complate: 368,
					avoidComplate: 368,
					totalComplate: 368
				}],
				listLoading:false
     		}
    }
  }
</script>

<style scoped>
	.toolbar .el-form-item {
		margin-bottom: 10px;
	}
	
	.toolbar {
		background: #fff;
	}
</style>