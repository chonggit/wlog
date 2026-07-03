# MRP例外信息查询表 Web API 操作原始内容

> 来源页面：全部 > 生产制造 > 计划管理 > MRP例外信息查询表

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 查询报表数据 | GetSysReportData | 2978 |

## 查询报表数据 (`GetSysReportData`)

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
client.GetSysReportData("PLN_MtrlSupplyDemandExpRpt","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FMrpBillNo":"","FComputeId":"","FMaterialEnd":{"FNumber":""},"FMaterialBegin":{"FNumber":""},"FOrgId":[{"FNumber":""}],"FQueryObject":[{"FID":""}],"FExceptionType":"","FMaterialIds":[{"FNumber":""}]}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FMrpBillNo": "",
        "FComputeId": "",
        "FMaterialEnd": {
            "FNumber": ""
        },
        "FMaterialBegin": {
            "FNumber": ""
        },
        "FOrgId": [
            {
                "FNumber": ""
            }
        ],
        "FQueryObject": [
            {
                "FID": ""
            }
        ],
        "FExceptionType": "",
        "FMaterialIds": [
            {
                "FNumber": ""
            }
        ]
    }
}

五、字段说明：
	 至：：FMaterialEnd 
	 物料编码：FMaterialBegin 
	 组织：FOrgId 
	 查询对象：FQueryObject 
	 例外类型：FExceptionType  (必填项)
	 运算编码：FMrpBillNo 
	 MRP运算单据内码：FComputeId 
	 物料编码：FMaterialIds 

参数FieldKeys显示列：
	 组织：FSupplyOrg 
	 单据：FBillName 
	 单据编号/行号：FBillNOAndSeq 
	 单据状态：FDocumentStatus 
	 物料编码：FMaterialNumber 
	 物料名称：FMaterialName 
	 规格型号：FMaterialModel 
	 BOM版本：FBomId 
	 计划跟踪号：FMtoNo 
	 辅助属性：FAuxPropName 
	 供应商：FSUPPLYID 
	 采购员：FPURCHERID 
	 单位：FUnitName 
	 计划数量：FPlanQty 
	 例外编码：FExpCode 
	 例外信息描述：FExpInfoDescription 
	 计划时间(完工/到货)：FPlanFinishDate 
	 建议日期(完工/到货)：FProposalFinishDate 
	 计划时间(采购/开工)：FPlanDate 
	 建议时间(采购/开工)：FProposalDate 
	 调整天数：FAdjustDay 
	 调整数量：FProposalQty 

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
