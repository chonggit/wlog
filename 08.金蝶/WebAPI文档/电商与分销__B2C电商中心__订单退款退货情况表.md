# 订单退款退货情况表 Web API 操作原始内容

> 来源页面：全部 > 电商与分销 > B2C电商中心 > 订单退款退货情况表

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 删除 | Delete | 3744 |
| 查看 | View | 3744 |
| 暂存 | Draft | 3744 |
| 保存 | Save | 3744 |
| 提交 | Submit | 3744 |
| 审核 | Audit | 3744 |
| 反审核 | UnAudit | 3744 |
| 禁用 | Forbid | 3744 |
| 反禁用 | Enable | 3744 |
| 撤销 | CancelAssign | 3744 |
| 批量保存 | BatchSave | 3744 |
| 单据查询 | ExecuteBillQuery | 3744 |
| 单据查询(json) | BillQuery | 3744 |
| 元数据查询 | QueryBusinessInfo | 3744 |
| 工作流审批 | WorkflowAudit | 3744 |
| 切换组织 | SwitchOrg | 3744 |

## 删除 (`Delete`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 查看 (`View`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 暂存 (`Draft`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 保存 (`Save`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 提交 (`Submit`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 审核 (`Audit`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 反审核 (`UnAudit`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 禁用 (`Forbid`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 反禁用 (`Enable`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 撤销 (`CancelAssign`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 批量保存 (`BatchSave`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 单据查询 (`ExecuteBillQuery`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 单据查询(json) (`BillQuery`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 元数据查询 (`QueryBusinessInfo`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 工作流审批 (`WorkflowAudit`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```

## 切换组织 (`SwitchOrg`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录）注（简单账表可能存在动态字段，指定待查字段时，须确保当前查询条件的结果集中包含待查字段）
     2.2.SchemeId：过滤方案内码，字符串类型
     2.3.StartRow：开始行索引，整型（非必录）
     2.4.Limit：最大行数，整型，不能超过10000（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认true（非必录）
     2.6.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     2.7.Model：表单数据包，JSON类型（必录）

二、返回结果：
{"Result": {"IsSuccess": true,"RowCount": 0,"Rows": [ ] }}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.GetSysReportData("ECC_OrderRefundList","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FNetOrderSource":{"FNUMBER":""},"FNetOrderBeginDate":"1900-01-01","FNetOrderEndDate":"1900-01-01","FBeginUserName":{"FNumber":""},"FEndUserName":{"FNumber":""},"FSaleOrgId":{"FNumber":""},"FEndSourceOrderNum":"","FEndGoodName":"","FBeginSourceOrderNum":"","FBeginGoodName":"","FBeginProxyMaterial":{"FNUMBER":""},"FEndProxyMaterial":{"FNUMBER":""},"FBeginBillNo":"","FEndBillNo":"","FColor0":"","FColor1":"","FColor2":"","FColor3":"","FRefundState":"","FHandleState":""}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FNetOrderSource": {
            "FNUMBER": ""
        },
        "FNetOrderBeginDate": "1900-01-01",
        "FNetOrderEndDate": "1900-01-01",
        "FBeginUserName": {
            "FNumber": ""
        },
        "FEndUserName": {
            "FNumber": ""
        },
        "FSaleOrgId": {
            "FNumber": ""
        },
        "FEndSourceOrderNum": "",
        "FEndGoodName": "",
        "FBeginSourceOrderNum": "",
        "FBeginGoodName": "",
        "FBeginProxyMaterial": {
            "FNUMBER": ""
        },
        "FEndProxyMaterial": {
            "FNUMBER": ""
        },
        "FBeginBillNo": "",
        "FEndBillNo": "",
        "FColor0": "",
        "FColor1": "",
        "FColor2": "",
        "FColor3": "",
        "FRefundState": "",
        "FHandleState": ""
    }
}

五、字段说明：
	 销售组织：FSaleOrgId 
	 来源网店：FNetOrderSource 
	 订单日期：FNetOrderBeginDate 
	 来源订单号：FBeginSourceOrderNum 
	 会员名称：FBeginUserName 
	 商品名称：FBeginGoodName 
	 物料：FBeginProxyMaterial 
	 订单编号：FBeginBillNo 
	 至：FNetOrderEndDate 
	 至：FEndSourceOrderNum 
	 至：FEndUserName 
	 至：FEndBillNo 
	 至：FEndGoodName 
	 至：FEndProxyMaterial 
	 颜色：FColor0 
	 颜色：FColor1 
	 颜色：FColor2 
	 颜色：FColor3 
	 退款/ 货状态：FRefundState 
	 线下处理状态：FHandleState 

参数FieldKeys显示列：
	 来源网店：FOnlineShop 
	 来源订单号：FSourceOrderNum 
	 订单编号：FBILLNO 
	 订单日期：FOrderDate 
	 会员名称：FMemberName 
	 商品名称：FGoodName 
	 物料编码：FNUMBER 
	 物料编码名称：FProxyMaterialName 
	 退款/ 货状态：FRefundStatus 
	 冻结状态：FIsFreeze 
	 关闭状态：FEntryCloseStatus 
	 线下处理状态：FEntryProcessStatus 
	 线上交易状态：FRecordStatus 
	 已关联出库数量：FStockRemoval 
	 数量：Fqty 
	 价税合计：FTaxAmount 
	 会员名称Id：FUserName 
	 来源网店Id：FNetSouece 
	 物料编码Id：FProxyMaterialId 

备注：错误代码MsgCode说明
           0：默认
           1：上下文丢失
           2：没有权限
           3：操作标识为空
           4：异常
           5：单据标识为空
           6：数据库操作失败
           7：许可错误
           8：参数错误
           9：指定字段/值不存在
           10：未找到对应数据
           11：验证失败
           12：不可操作
           13：网控冲突
           14：调用限制
           15：禁止管理员登录
```
