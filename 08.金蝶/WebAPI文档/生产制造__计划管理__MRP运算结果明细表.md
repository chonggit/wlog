# MRP运算结果明细表 Web API 操作原始内容

> 来源页面：全部 > 生产制造 > 计划管理 > MRP运算结果明细表

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 查询报表数据 | GetSysReportData | 3470 |

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
client.GetSysReportData("PLN_MRPCalDetailRpt","{"FieldKeys":"","SchemeId":"","StartRow":0,"Limit":2000,"IsVerifyBaseDataField":"true","FilterString":[],"Model":{"FStartDate":"1900-01-01","FMaterialEnd":{"FNumber":""},"FContainSubordinateMtrl":"false","FMaterialBegin":{"FNumber":""},"FEndDate":"1900-01-01","FMtrlCategory":"","FMrpBillNo":"","FComputeId":"","FMulOrgId":[{"FNumber":""}],"FPlanStrategy":"","FMtoNoBegin":"","FMtoNoEnd":"","FPlannerID":[{"FNumber":""}],"FPurchaserId":[{"FNumber":""}]}}");

四、JSON格式数据：
{
    "FieldKeys": "",
    "SchemeId": "",
    "StartRow": 0,
    "Limit": 2000,
    "IsVerifyBaseDataField": "true",
    "FilterString": [],
    "Model": {
        "FStartDate": "1900-01-01",
        "FMaterialEnd": {
            "FNumber": ""
        },
        "FContainSubordinateMtrl": "false",
        "FMaterialBegin": {
            "FNumber": ""
        },
        "FEndDate": "1900-01-01",
        "FMtrlCategory": "",
        "FMrpBillNo": "",
        "FComputeId": "",
        "FMulOrgId": [
            {
                "FNumber": ""
            }
        ],
        "FPlanStrategy": "",
        "FMtoNoBegin": "",
        "FMtoNoEnd": "",
        "FPlannerID": [
            {
                "FNumber": ""
            }
        ],
        "FPurchaserId": [
            {
                "FNumber": ""
            }
        ]
    }
}

五、字段说明：
	 日期：FStartDate 
	 至：：FMaterialEnd 
	 展开下级物料：FContainSubordinateMtrl 
	 物料编码：FMaterialBegin 
	 至：：FEndDate 
	 物料属性：FMtrlCategory  (必填项)
	 运算编码：FMrpBillNo  (必填项)
	 MRP运算单据内码：FComputeId 
	 查询组织：FMulOrgId 
	 计划策略：FPlanStrategy 
	 计划跟踪号：FMtoNoBegin 
	 至：FMtoNoEnd 
	 计划员：FPlannerID 
	 采购员：FPurchaserId 

参数FieldKeys显示列：
	 供需：FSupplyOrDemand 
	 业务组织：FBIZORGID 
	 单据类型：FSupplyFormId 
	 单据编号：FSupplyBillNo 
	 单据行号：FBillSeq 
	 物料编码：FMaterialId 
	 物料名称：FMaterialName 
	 规格型号：FMaterialModel 
	 基本单位：FBaseUnitId 
	 日期：FDemandDate 
	 BOM版本：FBomId 
	 计划跟踪号：FMtoNo 
	 辅助属性：FAuxPropId 
	 期初库存量：FOPENSTOCKQTY 
	 安全库存量：FSafeStockQty 
	 毛需求量：FGROSSREQUIREQTY 
	 预计入库量：FALLOWSTOCKQTY 
	 已分配量：FAllocatedQty 
	 净需求量：FNETCALCQTY 
	 计划订单量：FPLANORDERQTY 
	 组织间需求量：FROQty 
	 期末库存量：FCLOSESTOCKQTY 
	 仓库：FStockId 
	 仓位：FStockLocId 
	 即时库存：FINVSTOCKQTY 

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
