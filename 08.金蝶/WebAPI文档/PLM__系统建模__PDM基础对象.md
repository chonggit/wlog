# PDM基础对象 Web API 操作原始内容

> 来源页面：全部 > PLM > 系统建模 > PDM基础对象

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 删除对象 | Delete | 5090 |
| 查看 | View | 1093 |
| 保存 | Save | 5086 |
| 单据查询 | ExecuteBillQuery | 1876 |
| 单据查询(json) | BillQuery | 1861 |
| 元数据查询 | QueryBusinessInfo | 847 |
| 工作流审批 | WorkflowAudit | 1478 |
| 切换组织 | SwitchOrg | 1031 |

## 删除对象 (`Delete`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.opNumber：操作编码，字符串类型（必录）
3.data：JSON格式数据（详情参考JSON格式数据）（必录）
     3.1.Parameters：参数集合，字符串类型（非必录） 注（其值传给操作选项）
     3.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     3.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     3.4.Model：表单数据包，JSON类型（使用数据包时必录）
备注:
1.其中单据编码，单据内码，数据包必传其一；优先级：单据内码 > 单据编码 > 数据包。

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Delete("PLM_CFG_BASE","Delete","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FVerNO":"","FMinVerNO":"","FMaxVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FIsChange":"false","FIsChangeObject":"false","FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FCode": "",
        "FIcon": "",
        "FName": "",
        "FCreatorId": {
            "FUserID": ""
        },
        "FCreateDate": "1900-01-01",
        "FModifierId": {
            "FUserID": ""
        },
        "FModifyDate": "1900-01-01",
        "FCategoryID": {
            "FCODE": ""
        },
        "FFolderID": {
            "FCode": ""
        },
        "FLifeCircleStage": "",
        "FBATCH": 0,
        "FExtensionMark": "false",
        "FVerNO": "",
        "FMinVerNO": "",
        "FMaxVerNO": "",
        "FMaxVer": 0,
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FCheckOutor": {
            "FUserID": ""
        },
        "FIsFlow": 0,
        "FBASEOBJECTREF": 0,
        "FBuildVer": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FIsChange": "false",
        "FIsChangeObject": "false",
        "FAllowShare": "false",
        "FIsVirtualDoc": "false",
        "FECNFormId": {
            "FCODE": ""
        },
        "FCreateOrgId": {
            "FNumber": ""
        },
        "FGlobalShare": "false",
        "FIdentityKey": "",
        "FVerCreatorId": {
            "FUserID": ""
        },
        "FLastCheckin": {
            "FUserID": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FFLOWNUMBER": "",
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FFLOWCREATETIME": "1900-01-01",
        "FISINTERNALSAVE": "false",
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
PDM基础对象：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID  (必填项)
	 生命周期阶段：FLifeCircleStage  (必填项)
	 修改标记：FBATCH 
	 扩展标记：FExtensionMark 
	 版本号：FVerNO 
	 大版本序号：FMaxVer 
	 小版本序号：FMinVer 
	 检出标记：FIsCheckOut 
	 检出人：FCheckOutor 
	 是否在流程：FIsFlow 
	 关联对象：FBASEOBJECTREF 
	 版次：FBuildVer 
	 图标：FIcon 
	 名称：FName  (必填项)
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId 
	 分享到所有组织：FGlobalShare 
	 允许分享：FAllowShare 
	 关联附图的资源标识：FIdentityKey 
	 小版本号：FMinVerNO 
	 大版本号：FMaxVerNO 
	 版本创建人：FVerCreatorId 
	 最后检入人：FLastCheckin 
	 最后检入时间：FLastCheckinDate 
	 是否是内部保存件：FISINTERNALSAVE 
	 流程实例编号：FFLOWNUMBER 
	 流程名称：FPROCDEFID 
	 流程状态：FFLOWSTATUS 
	 发起人：FFLOWORIGINATORID 
	 发起时间：FFLOWCREATETIME 
	 传输任务编号：FTransUniqueKey 
	 检出日期：FCheckOutDate 

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
     2.1.CreateOrgId：创建者组织内码（非必录）
     2.2.Number：单据编码，字符串类型（使用编码时必录）
     2.3.Id：表单内码（使用内码时必录）
     2.4.IsSortBySeq：单据体是否按序号排序，默认false

二、返回结果：
{"Result":{"ResponseStatus":{"IsSuccess":"false"},"Result":"{}"}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.View("PLM_CFG_BASE","{"CreateOrgId":0,"Number":"","Id":"","IsSortBySeq":"false"}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Number": "",
    "Id": "",
    "IsSortBySeq": "false"
}


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
2.opNumber：操作编码，字符串类型（必录）
3.data：JSON格式数据（详情参考JSON格式数据）（必录）
     3.1.Parameters：参数集合，字符串类型（非必录） 注（其值传给操作选项）
     3.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     3.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     3.4.Model：表单数据包，JSON类型（使用数据包时必录）
备注:
1.其中单据编码，单据内码，数据包必传其一；优先级：单据内码 > 单据编码 > 数据包。

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Save("PLM_CFG_BASE","Save","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FVerNO":"","FMinVerNO":"","FMaxVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FIsChange":"false","FIsChangeObject":"false","FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FCode": "",
        "FIcon": "",
        "FName": "",
        "FCreatorId": {
            "FUserID": ""
        },
        "FCreateDate": "1900-01-01",
        "FModifierId": {
            "FUserID": ""
        },
        "FModifyDate": "1900-01-01",
        "FCategoryID": {
            "FCODE": ""
        },
        "FFolderID": {
            "FCode": ""
        },
        "FLifeCircleStage": "",
        "FBATCH": 0,
        "FExtensionMark": "false",
        "FVerNO": "",
        "FMinVerNO": "",
        "FMaxVerNO": "",
        "FMaxVer": 0,
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FCheckOutor": {
            "FUserID": ""
        },
        "FIsFlow": 0,
        "FBASEOBJECTREF": 0,
        "FBuildVer": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FIsChange": "false",
        "FIsChangeObject": "false",
        "FAllowShare": "false",
        "FIsVirtualDoc": "false",
        "FECNFormId": {
            "FCODE": ""
        },
        "FCreateOrgId": {
            "FNumber": ""
        },
        "FGlobalShare": "false",
        "FIdentityKey": "",
        "FVerCreatorId": {
            "FUserID": ""
        },
        "FLastCheckin": {
            "FUserID": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FFLOWNUMBER": "",
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FFLOWCREATETIME": "1900-01-01",
        "FISINTERNALSAVE": "false",
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
PDM基础对象：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID  (必填项)
	 生命周期阶段：FLifeCircleStage  (必填项)
	 修改标记：FBATCH 
	 扩展标记：FExtensionMark 
	 版本号：FVerNO 
	 大版本序号：FMaxVer 
	 小版本序号：FMinVer 
	 检出标记：FIsCheckOut 
	 检出人：FCheckOutor 
	 是否在流程：FIsFlow 
	 关联对象：FBASEOBJECTREF 
	 版次：FBuildVer 
	 图标：FIcon 
	 名称：FName  (必填项)
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId 
	 分享到所有组织：FGlobalShare 
	 允许分享：FAllowShare 
	 关联附图的资源标识：FIdentityKey 
	 小版本号：FMinVerNO 
	 大版本号：FMaxVerNO 
	 版本创建人：FVerCreatorId 
	 最后检入人：FLastCheckin 
	 最后检入时间：FLastCheckinDate 
	 是否是内部保存件：FISINTERNALSAVE 
	 流程实例编号：FFLOWNUMBER 
	 流程名称：FPROCDEFID 
	 流程状态：FFLOWSTATUS 
	 发起人：FFLOWORIGINATORID 
	 发起时间：FFLOWCREATETIME 
	 传输任务编号：FTransUniqueKey 
	 检出日期：FCheckOutDate 

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
1.data：JSON格式数据（详情参考JSON格式数据）（必录）
     1.1.FormId：业务对象表单Id（必录）
     1.2.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录） 注（查询单据体内码,需加单据体Key和下划线,如：FEntryKey_FEntryId）
     1.3.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     1.4.OrderString：排序字段，字符串类型（非必录）
     1.5.TopRowCount：返回总行数，整型（非必录）
     1.6.StartRow：开始行索引，整型（非必录）
     1.7.Limit：最大行数，整型，不能超过10000（非必录）
     1.8.SubSystemId：表单所在的子系统内码，字符串类型（非必录）

二、返回结果：
[["FValue1","FValue2",...],["FValue1","FValue2",...],...]

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.ExecuteBillQuery("{"FormId":"","FieldKeys":"","FilterString":[],"OrderString":"","TopRowCount":0,"StartRow":0,"Limit":2000,"SubSystemId":""}");

四、JSON格式数据：
{
    "FormId": "",
    "FieldKeys": "",
    "FilterString": [],
    "OrderString": "",
    "TopRowCount": 0,
    "StartRow": 0,
    "Limit": 2000,
    "SubSystemId": ""
}

五、参数FilterString说明：
 1、Left：左括号
 2、FieldName：字段名
 3、Compare：比较运算符内码，可通过"填写测试数据"功能生成
 4、Value：比较值
 5、Right：右括号
 6、Logic：逻辑运算符，0或1，0是AND，1是OR

六、参数FieldKeys特殊用法说明：
 1、查询单据内码：单据的主键字段名，如物料内码：FMATERIALID
 2、查询分录内码：单据体key_分录主键，如：FEntity_FEntryId
 3、查询分录行号：单据体key+序号字段标识，如：FEntity_FSeq

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
1.data：JSON格式数据（详情参考JSON格式数据）（必录）
     1.1.FormId：业务对象表单Id（必录）
     1.2.FieldKeys：需查询的字段key集合，字符串类型，格式："key1,key2,..."（必录） 注（查询单据体内码,需加单据体Key和下划线,如：FEntryKey_FEntryId）
     1.3.FilterString：过滤条件，数组类型，如：[{"Left":"(","FieldName":"Field1","Compare":"67","Value":"111","Right":")","Logic":"0"},{"Left":"(","FieldName":"Field2","Compare":"67","Value":"222","Right":")","Logic":"0"}]
     1.4.OrderString：排序字段，字符串类型（非必录）
     1.5.TopRowCount：返回总行数，整型（非必录）
     1.6.StartRow：开始行索引，整型（非必录）
     1.7.Limit：最大行数，整型，不能超过10000（非必录）
     1.8.SubSystemId：表单所在的子系统内码，字符串类型（非必录）

二、返回结果：
[{"Key1":"Value1",...},{"Key1":"Value1",...},...]

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.BillQuery("{"FormId":"","FieldKeys":"","FilterString":[],"OrderString":"","TopRowCount":0,"StartRow":0,"Limit":2000,"SubSystemId":""}");

四、JSON格式数据：
{
    "FormId": "",
    "FieldKeys": "",
    "FilterString": [],
    "OrderString": "",
    "TopRowCount": 0,
    "StartRow": 0,
    "Limit": 2000,
    "SubSystemId": ""
}

五、参数FilterString说明：
 1、Left：左括号
 2、FieldName：字段名
 3、Compare：比较运算符内码，可通过"填写测试数据"功能生成
 4、Value：比较值
 5、Right：右括号
 6、Logic：逻辑运算符，0或1，0是AND，1是OR

六、参数FieldKeys特殊用法说明：
 1、查询单据内码：单据的主键字段名，如物料内码：FMATERIALID
 2、查询分录内码：单据体key_分录主键，如：FEntity_FEntryId
 3、查询分录行号：单据体key+序号字段标识，如：FEntity_FSeq

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
1.data：JSON格式数据（详情参考JSON格式数据）（必录）
     1.1.FormId：业务对象表单Id（必录）

二、返回结果：
{"Result":{"ResponseStatus":"","NeedReturnData":"{}"}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.QueryBusinessInfo("{"FormId":"PLM_CFG_BASE"}");

四、JSON格式数据：
{
    "FormId": ""
}


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
1.data：JSON格式数据（详情参考JSON格式数据）（必录）
     1.1.FormId：业务对象表单Id（必录）
     1.2.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     1.3.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     1.4.UserId：审批人用户Id，整型
     1.5.UserName：用户名称，字符串类型
     1.6.ApprovalType：审批类型，整型（1：审批通过；2：驳回；3：终止）
     1.7.ActionResultId：审批项Id，字符串类型
     1.8.PostId：岗位Id，整型
     1.9.PostNumber：岗位编码，字符串类型
     1.10.Disposition：审批意见，字符串类型

二、返回结果：
{"Result":{"ResponseStatus":"","OperationResults":"{}"}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.WorkflowAudit("{"FormId":"","Ids":[],"Numbers":[],"UserId":0,"UserName":"","ApprovalType":0,"ActionResultId":"","PostId":0,"PostNumber":"","Disposition":""}");

四、JSON格式数据：
{
    "FormId": "",
    "Ids": [],
    "Numbers": [],
    "UserId": 0,
    "UserName": "",
    "ApprovalType": 0,
    "ActionResultId": "",
    "PostId": 0,
    "PostNumber": "",
    "Disposition": ""
}


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
1.data：JSON格式数据（详情参考JSON格式数据）（必录）
     1.1.OrgNumber：组织机构编码，字符串类型，（必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.SwitchOrg("{"OrgNumber":""}");

四、JSON格式数据：
{
    "OrgNumber": ""
}


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
