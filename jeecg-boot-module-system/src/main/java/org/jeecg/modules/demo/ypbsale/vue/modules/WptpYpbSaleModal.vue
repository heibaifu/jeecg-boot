<template>
  <a-modal
    :title="title"
    :width="width"
    :visible="visible"
    :confirmLoading="confirmLoading"
    @ok="handleOk"
    @cancel="handleCancel"
    cancelText="关闭">
    <a-spin :spinning="confirmLoading">
      <a-form :form="form">

        <a-form-item label="创建人名称" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'createName', validatorRules.createName]" placeholder="请输入创建人名称"></a-input>
        </a-form-item>
          
        <a-form-item label="创建人登录名称" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'createBy', validatorRules.createBy]" placeholder="请输入创建人登录名称"></a-input>
        </a-form-item>
          
        <a-form-item label="创建日期" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <j-date placeholder="请选择创建日期" v-decorator="[ 'createDate', validatorRules.createDate]" :trigger-change="true" style="width: 100%"/>
        </a-form-item>
          
        <a-form-item label="更新人名称" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'updateName', validatorRules.updateName]" placeholder="请输入更新人名称"></a-input>
        </a-form-item>
          
        <a-form-item label="更新人登录名称" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'updateBy', validatorRules.updateBy]" placeholder="请输入更新人登录名称"></a-input>
        </a-form-item>
          
        <a-form-item label="更新日期" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <j-date placeholder="请选择更新日期" v-decorator="[ 'updateDate', validatorRules.updateDate]" :trigger-change="true" style="width: 100%"/>
        </a-form-item>
          
        <a-form-item label="饮片销售流水号" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'saleNo', validatorRules.saleNo]" placeholder="请输入饮片销售流水号"></a-input>
        </a-form-item>
          
        <a-form-item label="追溯码" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'traceCode', validatorRules.traceCode]" placeholder="请输入追溯码"></a-input>
        </a-form-item>
          
        <a-form-item label="协会追溯码" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'xhTraceCode', validatorRules.xhTraceCode]" placeholder="请输入协会追溯码"></a-input>
        </a-form-item>
          
        <a-form-item label="种类编码" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'categoryCode', validatorRules.categoryCode]" placeholder="请输入种类编码"></a-input>
        </a-form-item>
          
        <a-form-item label="种类名称" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'categoryName', validatorRules.categoryName]" placeholder="请输入种类名称"></a-input>
        </a-form-item>
          
        <a-form-item label="饮片名称" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'ypName', validatorRules.ypName]" placeholder="请输入饮片名称"></a-input>
        </a-form-item>
          
        <a-form-item label="饮片规格" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'ypGuige', validatorRules.ypGuige]" placeholder="请输入饮片规格"></a-input>
        </a-form-item>
          
        <a-form-item label="饮片入库流水号" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'instockNo', validatorRules.instockNo]" placeholder="请输入饮片入库流水号"></a-input>
        </a-form-item>
          
        <a-form-item label="销售时间" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'saleTime', validatorRules.saleTime]" placeholder="请输入销售时间"></a-input>
        </a-form-item>
          
        <a-form-item label="销售数量" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input-number v-decorator="[ 'num', validatorRules.num]" placeholder="请输入销售数量" style="width: 100%"/>
        </a-form-item>
          
        <a-form-item label="出库时间" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'outTime', validatorRules.outTime]" placeholder="请输入出库时间"></a-input>
        </a-form-item>
          
        <a-form-item label="产品批号" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'productBatch', validatorRules.productBatch]" placeholder="请输入产品批号"></a-input>
        </a-form-item>
          
        <a-form-item label="客户" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'customer', validatorRules.customer]" placeholder="请输入客户"></a-input>
        </a-form-item>
          
        <a-form-item label="收货地址" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'address', validatorRules.address]" placeholder="请输入收货地址"></a-input>
        </a-form-item>
          
        <a-form-item label="审核标志" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'auditStatus', validatorRules.auditStatus]" placeholder="请输入审核标志"></a-input>
        </a-form-item>
          
        <a-form-item label="工作流" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'flowId', validatorRules.flowId]" placeholder="请输入工作流"></a-input>
        </a-form-item>
          
        <a-form-item label="删除标志" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'deleted', validatorRules.deleted]" placeholder="请输入删除标志"></a-input>
        </a-form-item>
          
        <a-form-item label="主机代码" :labelCol="labelCol" :wrapperCol="wrapperCol">
          <a-input v-decorator="[ 'hostCode', validatorRules.hostCode]" placeholder="请输入主机代码"></a-input>
        </a-form-item>
          
        
      </a-form>
    </a-spin>
  </a-modal>
</template>

<script>

  import { httpAction } from '@/api/manage'
  import pick from 'lodash.pick'
  import JDate from '@/components/jeecg/JDate'  
  
  export default {
    name: "WptpYpbSaleModal",
    components: { 
      JDate,
    },
    data () {
      return {
        form: this.$form.createForm(this),
        title:"操作",
        width:800,
        visible: false,
        model: {},
        labelCol: {
          xs: { span: 24 },
          sm: { span: 5 },
        },
        wrapperCol: {
          xs: { span: 24 },
          sm: { span: 16 },
        },

        confirmLoading: false,
        validatorRules:{
        createName:{},
        createBy:{},
        createDate:{},
        updateName:{},
        updateBy:{},
        updateDate:{},
        saleNo:{},
        traceCode:{},
        xhTraceCode:{},
        categoryCode:{},
        categoryName:{},
        ypName:{},
        ypGuige:{},
        instockNo:{},
        saleTime:{},
        num:{},
        outTime:{},
        productBatch:{},
        customer:{},
        address:{},
        auditStatus:{},
        flowId:{},
        deleted:{},
        hostCode:{},
        },
        url: {
          add: "/ypbsale/wptpYpbSale/add",
          edit: "/ypbsale/wptpYpbSale/edit",
        }
     
      }
    },
    created () {
    },
    methods: {
      add () {
        this.edit({});
      },
      edit (record) {
        this.form.resetFields();
        this.model = Object.assign({}, record);
        this.visible = true;
        this.$nextTick(() => {
          this.form.setFieldsValue(pick(this.model,'createName','createBy','createDate','updateName','updateBy','updateDate','saleNo','traceCode','xhTraceCode','categoryCode','categoryName','ypName','ypGuige','instockNo','saleTime','num','outTime','productBatch','customer','address','auditStatus','flowId','deleted','hostCode'))
        })
      },
      close () {
        this.$emit('close');
        this.visible = false;
      },
      handleOk () {
        const that = this;
        // 触发表单验证
        this.form.validateFields((err, values) => {
          if (!err) {
            that.confirmLoading = true;
            let httpurl = '';
            let method = '';
            if(!this.model.id){
              httpurl+=this.url.add;
              method = 'post';
            }else{
              httpurl+=this.url.edit;
               method = 'put';
            }
            let formData = Object.assign(this.model, values);
            console.log("表单提交数据",formData)
            httpAction(httpurl,formData,method).then((res)=>{
              if(res.success){
                that.$message.success(res.message);
                that.$emit('ok');
              }else{
                that.$message.warning(res.message);
              }
            }).finally(() => {
              that.confirmLoading = false;
              that.close();
            })
          }
         
        })
      },
      handleCancel () {
        this.close()
      },
      popupCallback(row){
        this.form.setFieldsValue(pick(row,'createName','createBy','createDate','updateName','updateBy','updateDate','saleNo','traceCode','xhTraceCode','categoryCode','categoryName','ypName','ypGuige','instockNo','saleTime','num','outTime','productBatch','customer','address','auditStatus','flowId','deleted','hostCode'))
      }
      
    }
  }
</script>