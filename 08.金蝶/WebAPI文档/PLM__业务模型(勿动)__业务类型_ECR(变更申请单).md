# 业务类型_ECR(变更申请单) Web API 操作原始内容

> 来源页面：全部 > PLM > 业务模型(勿动) > 业务类型_ECR(变更申请单)

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 删除对象 | Delete | 9618 |
| 查看 | View | 1108 |
| 保存 | Save | 9614 |
| 下推变更单 | EcrSynToEcn | 9632 |
| 反审核 | UnAudit | 1779 |
| 审核 | Audit | 9616 |
| 审核 | PLMOP_1054_AL | 9634 |
| 单据查询 | ExecuteBillQuery | 1876 |
| 单据查询(json) | BillQuery | 1861 |
| 元数据查询 | QueryBusinessInfo | 862 |
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
client.Delete("PLM_PDM_1070100000000000000","Delete","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FMaxVerNO":"","FMinVerNO":"","FVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FRemark":"","FIsChange":"false","FApplicant":{"FUSERACCOUNT":""},"FIsChangeObject":"false","FApplyDepartment":{"FNUMBER":""},"FChargeUserId":{"FUSERACCOUNT":""},"FCustomer":{"FNUMBER":""},"FApllyDate":"1900-01-01","FCompleteDate":"1900-01-01","FAuditDate":"1900-01-01","FChangeSource":"","FIsStandard":"false","FChangeReason":"","FPriceEx":0,"FApplyOrganization":{"FNUMBER":""},"FFinishRate":0,"FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01","FEntityAtt":[{"FEntryID":0,"FAttachObjectIcon":"","FAttachObject":{"FCODE":""},"FType":""}],"FChangeObjectEntity":[{"FEntryID":0,"FROWID":"","FPARENTROWID":"","FROWEXPANDTYPE":"","FIsSelect":"false","FBaseObject":0,"FItemType":"","FEntryIcon":"","FObjectCode":"","FObjectName":"","FObjectCategory":{"FName":""},"FObjectVerNo":"","FObjectType":"","FModifyReport":"","FIsFinish":"false","FIsSync":"false","FObjectMaxVer":0,"FOBJECTMINVER":0,"FObjectBuildVer":0,"FRefVersionId":0,"FERPBillCode":"","FInventory":"","FDescription":"","FObjectIcon":"","FChangeObject":{"FCODE":""},"FSyncErpMode":"","FBatchSubstitutionDetail":[{"FDetailID":0,"FBS_BOMObject":{"FCODE":""},"FBS_BomRefVersionId":0,"FBS_BomNewVersionId":0}]}]}}");

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
        "FMaxVerNO": "",
        "FMinVerNO": "",
        "FVerNO": "",
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
        "FRemark": "",
        "FIsChange": "false",
        "FApplicant": {
            "FUSERACCOUNT": ""
        },
        "FIsChangeObject": "false",
        "FApplyDepartment": {
            "FNUMBER": ""
        },
        "FChargeUserId": {
            "FUSERACCOUNT": ""
        },
        "FCustomer": {
            "FNUMBER": ""
        },
        "FApllyDate": "1900-01-01",
        "FCompleteDate": "1900-01-01",
        "FAuditDate": "1900-01-01",
        "FChangeSource": "",
        "FIsStandard": "false",
        "FChangeReason": "",
        "FPriceEx": 0,
        "FApplyOrganization": {
            "FNUMBER": ""
        },
        "FFinishRate": 0,
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
        "FCheckOutDate": "1900-01-01",
        "FEntityAtt": [
            {
                "FEntryID": 0,
                "FAttachObjectIcon": "",
                "FAttachObject": {
                    "FCODE": ""
                },
                "FType": ""
            }
        ],
        "FChangeObjectEntity": [
            {
                "FEntryID": 0,
                "FROWID": "",
                "FPARENTROWID": "",
                "FROWEXPANDTYPE": "",
                "FIsSelect": "false",
                "FBaseObject": 0,
                "FItemType": "",
                "FEntryIcon": "",
                "FObjectCode": "",
                "FObjectName": "",
                "FObjectCategory": {
                    "FName": ""
                },
                "FObjectVerNo": "",
                "FObjectType": "",
                "FModifyReport": "",
                "FIsFinish": "false",
                "FIsSync": "false",
                "FObjectMaxVer": 0,
                "FOBJECTMINVER": 0,
                "FObjectBuildVer": 0,
                "FRefVersionId": 0,
                "FERPBillCode": "",
                "FInventory": "",
                "FDescription": "",
                "FObjectIcon": "",
                "FChangeObject": {
                    "FCODE": ""
                },
                "FSyncErpMode": "",
                "FBatchSubstitutionDetail": [
                    {
                        "FDetailID": 0,
                        "FBS_BOMObject": {
                            "FCODE": ""
                        },
                        "FBS_BomRefVersionId": 0,
                        "FBS_BomNewVersionId": 0
                    }
                ]
            }
        ]
    }
}

五、字段说明：
变更申请单：FBillHead 
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
	 名称：FName 
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId  (必填项)
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
	 变更内容：FRemark 
	 申请人：FApplicant  (必填项)
	 申请部门：FApplyDepartment 
	 客户：FCustomer 
	 申请日期：FApllyDate 
	 变更原因：FChangeReason 
	 申请组织：FApplyOrganization 
	 完成日期：FCompleteDate 
	 审核日期：FAuditDate 
	 变更来源：FChangeSource 
	 负责人：FChargeUserId 
	 完成进度：FFinishRate 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
附件：FEntityAtt 
	 实体主键：FEntryID 
	 文档编码：FAttachObject  (必填项)
	 文档名称：FAttachObjectName 
	 文档图标：FAttachObjectIcon 
	 附件类型：FType 
变更对象：FChangeObjectEntity 
	 实体主键：FEntryID 
	 主键：FROWID 
	 父级内码：FPARENTROWID 
	 行类型：FROWEXPANDTYPE 
	 变更对象标识：FBaseObject 
	 图标：FEntryIcon 
	 对象编码：FObjectCode 
	 对象名称：FObjectName 
	 版本标识：FObjectVerNo 
	 变更项类型：FItemType 
	 修改描述：FDescription 
	 执行描述：FOperation 
	 执行人：FAssign 
	 是否完成：FIsFinish 
	 是否下推同步：FIsSync 
	 主版本号：FObjectMaxVer 
	 次版本号：FOBJECTMINVER 
	 版次号：FObjectBuildVer 
	 变更对象类型：FObjectType 
	 是否选中：FIsSelect 
	 业务类型：FObjectCategory 
	 原版本标识：FRefVersionId 
	 ERP单据编码：FERPBillCode 
	 数量：FInventory 
	 修改报告：FModifyReport 
	 对象图标字符：FObjectIcon 
	 变更对象：FChangeObject 
	 下推方式：FSyncErpMode 
批量替换详情：FBatchSubstitutionDetail 
	 实体主键：FDetailID 
	 BOM对象：FBS_BOMObject 
	 BOM原版本标识：FBS_BomRefVersionId 
	 BOM新版本标识：FBS_BomNewVersionId 

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
client.View("PLM_PDM_1070100000000000000","{"CreateOrgId":0,"Number":"","Id":"","IsSortBySeq":"false"}");

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
client.Save("PLM_PDM_1070100000000000000","Save","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FMaxVerNO":"","FMinVerNO":"","FVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FRemark":"","FIsChange":"false","FApplicant":{"FUSERACCOUNT":""},"FIsChangeObject":"false","FApplyDepartment":{"FNUMBER":""},"FChargeUserId":{"FUSERACCOUNT":""},"FCustomer":{"FNUMBER":""},"FApllyDate":"1900-01-01","FCompleteDate":"1900-01-01","FAuditDate":"1900-01-01","FChangeSource":"","FIsStandard":"false","FChangeReason":"","FPriceEx":0,"FApplyOrganization":{"FNUMBER":""},"FFinishRate":0,"FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01","FEntityAtt":[{"FEntryID":0,"FAttachObjectIcon":"","FAttachObject":{"FCODE":""},"FType":""}],"FChangeObjectEntity":[{"FEntryID":0,"FROWID":"","FPARENTROWID":"","FROWEXPANDTYPE":"","FIsSelect":"false","FBaseObject":0,"FItemType":"","FEntryIcon":"","FObjectCode":"","FObjectName":"","FObjectCategory":{"FName":""},"FObjectVerNo":"","FObjectType":"","FModifyReport":"","FIsFinish":"false","FIsSync":"false","FObjectMaxVer":0,"FOBJECTMINVER":0,"FObjectBuildVer":0,"FRefVersionId":0,"FERPBillCode":"","FInventory":"","FDescription":"","FObjectIcon":"","FChangeObject":{"FCODE":""},"FSyncErpMode":"","FBatchSubstitutionDetail":[{"FDetailID":0,"FBS_BOMObject":{"FCODE":""},"FBS_BomRefVersionId":0,"FBS_BomNewVersionId":0}]}]}}");

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
        "FMaxVerNO": "",
        "FMinVerNO": "",
        "FVerNO": "",
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
        "FRemark": "",
        "FIsChange": "false",
        "FApplicant": {
            "FUSERACCOUNT": ""
        },
        "FIsChangeObject": "false",
        "FApplyDepartment": {
            "FNUMBER": ""
        },
        "FChargeUserId": {
            "FUSERACCOUNT": ""
        },
        "FCustomer": {
            "FNUMBER": ""
        },
        "FApllyDate": "1900-01-01",
        "FCompleteDate": "1900-01-01",
        "FAuditDate": "1900-01-01",
        "FChangeSource": "",
        "FIsStandard": "false",
        "FChangeReason": "",
        "FPriceEx": 0,
        "FApplyOrganization": {
            "FNUMBER": ""
        },
        "FFinishRate": 0,
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
        "FCheckOutDate": "1900-01-01",
        "FEntityAtt": [
            {
                "FEntryID": 0,
                "FAttachObjectIcon": "",
                "FAttachObject": {
                    "FCODE": ""
                },
                "FType": ""
            }
        ],
        "FChangeObjectEntity": [
            {
                "FEntryID": 0,
                "FROWID": "",
                "FPARENTROWID": "",
                "FROWEXPANDTYPE": "",
                "FIsSelect": "false",
                "FBaseObject": 0,
                "FItemType": "",
                "FEntryIcon": "",
                "FObjectCode": "",
                "FObjectName": "",
                "FObjectCategory": {
                    "FName": ""
                },
                "FObjectVerNo": "",
                "FObjectType": "",
                "FModifyReport": "",
                "FIsFinish": "false",
                "FIsSync": "false",
                "FObjectMaxVer": 0,
                "FOBJECTMINVER": 0,
                "FObjectBuildVer": 0,
                "FRefVersionId": 0,
                "FERPBillCode": "",
                "FInventory": "",
                "FDescription": "",
                "FObjectIcon": "",
                "FChangeObject": {
                    "FCODE": ""
                },
                "FSyncErpMode": "",
                "FBatchSubstitutionDetail": [
                    {
                        "FDetailID": 0,
                        "FBS_BOMObject": {
                            "FCODE": ""
                        },
                        "FBS_BomRefVersionId": 0,
                        "FBS_BomNewVersionId": 0
                    }
                ]
            }
        ]
    }
}

五、字段说明：
变更申请单：FBillHead 
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
	 名称：FName 
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId  (必填项)
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
	 变更内容：FRemark 
	 申请人：FApplicant  (必填项)
	 申请部门：FApplyDepartment 
	 客户：FCustomer 
	 申请日期：FApllyDate 
	 变更原因：FChangeReason 
	 申请组织：FApplyOrganization 
	 完成日期：FCompleteDate 
	 审核日期：FAuditDate 
	 变更来源：FChangeSource 
	 负责人：FChargeUserId 
	 完成进度：FFinishRate 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
附件：FEntityAtt 
	 实体主键：FEntryID 
	 文档编码：FAttachObject  (必填项)
	 文档名称：FAttachObjectName 
	 文档图标：FAttachObjectIcon 
	 附件类型：FType 
变更对象：FChangeObjectEntity 
	 实体主键：FEntryID 
	 主键：FROWID 
	 父级内码：FPARENTROWID 
	 行类型：FROWEXPANDTYPE 
	 变更对象标识：FBaseObject 
	 图标：FEntryIcon 
	 对象编码：FObjectCode 
	 对象名称：FObjectName 
	 版本标识：FObjectVerNo 
	 变更项类型：FItemType 
	 修改描述：FDescription 
	 执行描述：FOperation 
	 执行人：FAssign 
	 是否完成：FIsFinish 
	 是否下推同步：FIsSync 
	 主版本号：FObjectMaxVer 
	 次版本号：FOBJECTMINVER 
	 版次号：FObjectBuildVer 
	 变更对象类型：FObjectType 
	 是否选中：FIsSelect 
	 业务类型：FObjectCategory 
	 原版本标识：FRefVersionId 
	 ERP单据编码：FERPBillCode 
	 数量：FInventory 
	 修改报告：FModifyReport 
	 对象图标字符：FObjectIcon 
	 变更对象：FChangeObject 
	 下推方式：FSyncErpMode 
批量替换详情：FBatchSubstitutionDetail 
	 实体主键：FDetailID 
	 BOM对象：FBS_BOMObject 
	 BOM原版本标识：FBS_BomRefVersionId 
	 BOM新版本标识：FBS_BomNewVersionId 

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

## 下推变更单 (`EcrSynToEcn`)

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
client.ExcuteOperation("PLM_PDM_1070100000000000000","EcrSynToEcn","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FMaxVerNO":"","FMinVerNO":"","FVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FRemark":"","FIsChange":"false","FApplicant":{"FUSERACCOUNT":""},"FIsChangeObject":"false","FApplyDepartment":{"FNUMBER":""},"FChargeUserId":{"FUSERACCOUNT":""},"FCustomer":{"FNUMBER":""},"FApllyDate":"1900-01-01","FCompleteDate":"1900-01-01","FAuditDate":"1900-01-01","FChangeSource":"","FIsStandard":"false","FChangeReason":"","FPriceEx":0,"FApplyOrganization":{"FNUMBER":""},"FFinishRate":0,"FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01","FEntityAtt":[{"FEntryID":0,"FAttachObjectIcon":"","FAttachObject":{"FCODE":""},"FType":""}],"FChangeObjectEntity":[{"FEntryID":0,"FROWID":"","FPARENTROWID":"","FROWEXPANDTYPE":"","FIsSelect":"false","FBaseObject":0,"FItemType":"","FEntryIcon":"","FObjectCode":"","FObjectName":"","FObjectCategory":{"FName":""},"FObjectVerNo":"","FObjectType":"","FModifyReport":"","FIsFinish":"false","FIsSync":"false","FObjectMaxVer":0,"FOBJECTMINVER":0,"FObjectBuildVer":0,"FRefVersionId":0,"FERPBillCode":"","FInventory":"","FDescription":"","FObjectIcon":"","FChangeObject":{"FCODE":""},"FSyncErpMode":"","FBatchSubstitutionDetail":[{"FDetailID":0,"FBS_BOMObject":{"FCODE":""},"FBS_BomRefVersionId":0,"FBS_BomNewVersionId":0}]}]}}");

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
        "FMaxVerNO": "",
        "FMinVerNO": "",
        "FVerNO": "",
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
        "FRemark": "",
        "FIsChange": "false",
        "FApplicant": {
            "FUSERACCOUNT": ""
        },
        "FIsChangeObject": "false",
        "FApplyDepartment": {
            "FNUMBER": ""
        },
        "FChargeUserId": {
            "FUSERACCOUNT": ""
        },
        "FCustomer": {
            "FNUMBER": ""
        },
        "FApllyDate": "1900-01-01",
        "FCompleteDate": "1900-01-01",
        "FAuditDate": "1900-01-01",
        "FChangeSource": "",
        "FIsStandard": "false",
        "FChangeReason": "",
        "FPriceEx": 0,
        "FApplyOrganization": {
            "FNUMBER": ""
        },
        "FFinishRate": 0,
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
        "FCheckOutDate": "1900-01-01",
        "FEntityAtt": [
            {
                "FEntryID": 0,
                "FAttachObjectIcon": "",
                "FAttachObject": {
                    "FCODE": ""
                },
                "FType": ""
            }
        ],
        "FChangeObjectEntity": [
            {
                "FEntryID": 0,
                "FROWID": "",
                "FPARENTROWID": "",
                "FROWEXPANDTYPE": "",
                "FIsSelect": "false",
                "FBaseObject": 0,
                "FItemType": "",
                "FEntryIcon": "",
                "FObjectCode": "",
                "FObjectName": "",
                "FObjectCategory": {
                    "FName": ""
                },
                "FObjectVerNo": "",
                "FObjectType": "",
                "FModifyReport": "",
                "FIsFinish": "false",
                "FIsSync": "false",
                "FObjectMaxVer": 0,
                "FOBJECTMINVER": 0,
                "FObjectBuildVer": 0,
                "FRefVersionId": 0,
                "FERPBillCode": "",
                "FInventory": "",
                "FDescription": "",
                "FObjectIcon": "",
                "FChangeObject": {
                    "FCODE": ""
                },
                "FSyncErpMode": "",
                "FBatchSubstitutionDetail": [
                    {
                        "FDetailID": 0,
                        "FBS_BOMObject": {
                            "FCODE": ""
                        },
                        "FBS_BomRefVersionId": 0,
                        "FBS_BomNewVersionId": 0
                    }
                ]
            }
        ]
    }
}

五、字段说明：
变更申请单：FBillHead 
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
	 名称：FName 
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId  (必填项)
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
	 变更内容：FRemark 
	 申请人：FApplicant  (必填项)
	 申请部门：FApplyDepartment 
	 客户：FCustomer 
	 申请日期：FApllyDate 
	 变更原因：FChangeReason 
	 申请组织：FApplyOrganization 
	 完成日期：FCompleteDate 
	 审核日期：FAuditDate 
	 变更来源：FChangeSource 
	 负责人：FChargeUserId 
	 完成进度：FFinishRate 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
附件：FEntityAtt 
	 实体主键：FEntryID 
	 文档编码：FAttachObject  (必填项)
	 文档名称：FAttachObjectName 
	 文档图标：FAttachObjectIcon 
	 附件类型：FType 
变更对象：FChangeObjectEntity 
	 实体主键：FEntryID 
	 主键：FROWID 
	 父级内码：FPARENTROWID 
	 行类型：FROWEXPANDTYPE 
	 变更对象标识：FBaseObject 
	 图标：FEntryIcon 
	 对象编码：FObjectCode 
	 对象名称：FObjectName 
	 版本标识：FObjectVerNo 
	 变更项类型：FItemType 
	 修改描述：FDescription 
	 执行描述：FOperation 
	 执行人：FAssign 
	 是否完成：FIsFinish 
	 是否下推同步：FIsSync 
	 主版本号：FObjectMaxVer 
	 次版本号：FOBJECTMINVER 
	 版次号：FObjectBuildVer 
	 变更对象类型：FObjectType 
	 是否选中：FIsSelect 
	 业务类型：FObjectCategory 
	 原版本标识：FRefVersionId 
	 ERP单据编码：FERPBillCode 
	 数量：FInventory 
	 修改报告：FModifyReport 
	 对象图标字符：FObjectIcon 
	 变更对象：FChangeObject 
	 下推方式：FSyncErpMode 
批量替换详情：FBatchSubstitutionDetail 
	 实体主键：FDetailID 
	 BOM对象：FBS_BOMObject 
	 BOM原版本标识：FBS_BomRefVersionId 
	 BOM新版本标识：FBS_BomNewVersionId 

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
     2.1.CreateOrgId：创建者组织内码（非必录）
     2.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     2.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     2.4.InterationFlags：交互标志集合，字符串类型，分号分隔，格式："flag1;flag2;..."（非必录） 例如（允许负库存标识：STK_InvCheckResult）
     2.5.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）
     2.6.UseOrgId：使用者组织内码（非必录）
     2.7.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）
     2.8.IsVerifyProcInst：是否检验单据关联运行中的工作流实例，布尔类型，默认true（非必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.UnAudit("PLM_PDM_1070100000000000000","{"CreateOrgId":0,"Numbers":[],"Ids":"","InterationFlags":"","IgnoreInterationFlag":"","UseOrgId":0,"NetworkCtrl":"","IsVerifyProcInst":"true"}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "InterationFlags": "",
    "IgnoreInterationFlag": "",
    "UseOrgId": 0,
    "NetworkCtrl": "",
    "IsVerifyProcInst": "true"
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

## 审核 (`Audit`)

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
client.Audit("PLM_PDM_1070100000000000000","Audit","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FMaxVerNO":"","FMinVerNO":"","FVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FRemark":"","FIsChange":"false","FApplicant":{"FUSERACCOUNT":""},"FIsChangeObject":"false","FApplyDepartment":{"FNUMBER":""},"FChargeUserId":{"FUSERACCOUNT":""},"FCustomer":{"FNUMBER":""},"FApllyDate":"1900-01-01","FCompleteDate":"1900-01-01","FAuditDate":"1900-01-01","FChangeSource":"","FIsStandard":"false","FChangeReason":"","FPriceEx":0,"FApplyOrganization":{"FNUMBER":""},"FFinishRate":0,"FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01","FEntityAtt":[{"FEntryID":0,"FAttachObjectIcon":"","FAttachObject":{"FCODE":""},"FType":""}],"FChangeObjectEntity":[{"FEntryID":0,"FROWID":"","FPARENTROWID":"","FROWEXPANDTYPE":"","FIsSelect":"false","FBaseObject":0,"FItemType":"","FEntryIcon":"","FObjectCode":"","FObjectName":"","FObjectCategory":{"FName":""},"FObjectVerNo":"","FObjectType":"","FModifyReport":"","FIsFinish":"false","FIsSync":"false","FObjectMaxVer":0,"FOBJECTMINVER":0,"FObjectBuildVer":0,"FRefVersionId":0,"FERPBillCode":"","FInventory":"","FDescription":"","FObjectIcon":"","FChangeObject":{"FCODE":""},"FSyncErpMode":"","FBatchSubstitutionDetail":[{"FDetailID":0,"FBS_BOMObject":{"FCODE":""},"FBS_BomRefVersionId":0,"FBS_BomNewVersionId":0}]}]}}");

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
        "FMaxVerNO": "",
        "FMinVerNO": "",
        "FVerNO": "",
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
        "FRemark": "",
        "FIsChange": "false",
        "FApplicant": {
            "FUSERACCOUNT": ""
        },
        "FIsChangeObject": "false",
        "FApplyDepartment": {
            "FNUMBER": ""
        },
        "FChargeUserId": {
            "FUSERACCOUNT": ""
        },
        "FCustomer": {
            "FNUMBER": ""
        },
        "FApllyDate": "1900-01-01",
        "FCompleteDate": "1900-01-01",
        "FAuditDate": "1900-01-01",
        "FChangeSource": "",
        "FIsStandard": "false",
        "FChangeReason": "",
        "FPriceEx": 0,
        "FApplyOrganization": {
            "FNUMBER": ""
        },
        "FFinishRate": 0,
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
        "FCheckOutDate": "1900-01-01",
        "FEntityAtt": [
            {
                "FEntryID": 0,
                "FAttachObjectIcon": "",
                "FAttachObject": {
                    "FCODE": ""
                },
                "FType": ""
            }
        ],
        "FChangeObjectEntity": [
            {
                "FEntryID": 0,
                "FROWID": "",
                "FPARENTROWID": "",
                "FROWEXPANDTYPE": "",
                "FIsSelect": "false",
                "FBaseObject": 0,
                "FItemType": "",
                "FEntryIcon": "",
                "FObjectCode": "",
                "FObjectName": "",
                "FObjectCategory": {
                    "FName": ""
                },
                "FObjectVerNo": "",
                "FObjectType": "",
                "FModifyReport": "",
                "FIsFinish": "false",
                "FIsSync": "false",
                "FObjectMaxVer": 0,
                "FOBJECTMINVER": 0,
                "FObjectBuildVer": 0,
                "FRefVersionId": 0,
                "FERPBillCode": "",
                "FInventory": "",
                "FDescription": "",
                "FObjectIcon": "",
                "FChangeObject": {
                    "FCODE": ""
                },
                "FSyncErpMode": "",
                "FBatchSubstitutionDetail": [
                    {
                        "FDetailID": 0,
                        "FBS_BOMObject": {
                            "FCODE": ""
                        },
                        "FBS_BomRefVersionId": 0,
                        "FBS_BomNewVersionId": 0
                    }
                ]
            }
        ]
    }
}

五、字段说明：
变更申请单：FBillHead 
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
	 名称：FName 
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId  (必填项)
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
	 变更内容：FRemark 
	 申请人：FApplicant  (必填项)
	 申请部门：FApplyDepartment 
	 客户：FCustomer 
	 申请日期：FApllyDate 
	 变更原因：FChangeReason 
	 申请组织：FApplyOrganization 
	 完成日期：FCompleteDate 
	 审核日期：FAuditDate 
	 变更来源：FChangeSource 
	 负责人：FChargeUserId 
	 完成进度：FFinishRate 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
附件：FEntityAtt 
	 实体主键：FEntryID 
	 文档编码：FAttachObject  (必填项)
	 文档名称：FAttachObjectName 
	 文档图标：FAttachObjectIcon 
	 附件类型：FType 
变更对象：FChangeObjectEntity 
	 实体主键：FEntryID 
	 主键：FROWID 
	 父级内码：FPARENTROWID 
	 行类型：FROWEXPANDTYPE 
	 变更对象标识：FBaseObject 
	 图标：FEntryIcon 
	 对象编码：FObjectCode 
	 对象名称：FObjectName 
	 版本标识：FObjectVerNo 
	 变更项类型：FItemType 
	 修改描述：FDescription 
	 执行描述：FOperation 
	 执行人：FAssign 
	 是否完成：FIsFinish 
	 是否下推同步：FIsSync 
	 主版本号：FObjectMaxVer 
	 次版本号：FOBJECTMINVER 
	 版次号：FObjectBuildVer 
	 变更对象类型：FObjectType 
	 是否选中：FIsSelect 
	 业务类型：FObjectCategory 
	 原版本标识：FRefVersionId 
	 ERP单据编码：FERPBillCode 
	 数量：FInventory 
	 修改报告：FModifyReport 
	 对象图标字符：FObjectIcon 
	 变更对象：FChangeObject 
	 下推方式：FSyncErpMode 
批量替换详情：FBatchSubstitutionDetail 
	 实体主键：FDetailID 
	 BOM对象：FBS_BOMObject 
	 BOM原版本标识：FBS_BomRefVersionId 
	 BOM新版本标识：FBS_BomNewVersionId 

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

## 审核 (`PLMOP_1054_AL`)

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
client.ExcuteOperation("PLM_PDM_1070100000000000000","PLMOP_1054_AL","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FCode":"","FIcon":"","FName":"","FCreatorId":{"FUserID":""},"FCreateDate":"1900-01-01","FModifierId":{"FUserID":""},"FModifyDate":"1900-01-01","FCategoryID":{"FCODE":""},"FFolderID":{"FCode":""},"FLifeCircleStage":"","FBATCH":0,"FExtensionMark":"false","FMaxVerNO":"","FMinVerNO":"","FVerNO":"","FMaxVer":0,"FMinVer":0,"FIsCheckOut":"false","FCheckOutor":{"FUserID":""},"FIsFlow":0,"FBASEOBJECTREF":0,"FBuildVer":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FChangeObjectId":{"FCODE":""},"FRemark":"","FIsChange":"false","FApplicant":{"FUSERACCOUNT":""},"FIsChangeObject":"false","FApplyDepartment":{"FNUMBER":""},"FChargeUserId":{"FUSERACCOUNT":""},"FCustomer":{"FNUMBER":""},"FApllyDate":"1900-01-01","FCompleteDate":"1900-01-01","FAuditDate":"1900-01-01","FChangeSource":"","FIsStandard":"false","FChangeReason":"","FPriceEx":0,"FApplyOrganization":{"FNUMBER":""},"FFinishRate":0,"FAllowShare":"false","FIsVirtualDoc":"false","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FLastCheckin":{"FUserID":""},"FLastCheckinDate":"1900-01-01","FFLOWNUMBER":"","FPROCDEFID":{"FDISPLAYNAME":""},"FFLOWSTATUS":"","FFLOWORIGINATORID":{"FUserID":""},"FFLOWCREATETIME":"1900-01-01","FISINTERNALSAVE":"false","FTransUniqueKey":"","FCheckOutDate":"1900-01-01","FEntityAtt":[{"FEntryID":0,"FAttachObjectIcon":"","FAttachObject":{"FCODE":""},"FType":""}],"FChangeObjectEntity":[{"FEntryID":0,"FROWID":"","FPARENTROWID":"","FROWEXPANDTYPE":"","FIsSelect":"false","FBaseObject":0,"FItemType":"","FEntryIcon":"","FObjectCode":"","FObjectName":"","FObjectCategory":{"FName":""},"FObjectVerNo":"","FObjectType":"","FModifyReport":"","FIsFinish":"false","FIsSync":"false","FObjectMaxVer":0,"FOBJECTMINVER":0,"FObjectBuildVer":0,"FRefVersionId":0,"FERPBillCode":"","FInventory":"","FDescription":"","FObjectIcon":"","FChangeObject":{"FCODE":""},"FSyncErpMode":"","FBatchSubstitutionDetail":[{"FDetailID":0,"FBS_BOMObject":{"FCODE":""},"FBS_BomRefVersionId":0,"FBS_BomNewVersionId":0}]}]}}");

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
        "FMaxVerNO": "",
        "FMinVerNO": "",
        "FVerNO": "",
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
        "FRemark": "",
        "FIsChange": "false",
        "FApplicant": {
            "FUSERACCOUNT": ""
        },
        "FIsChangeObject": "false",
        "FApplyDepartment": {
            "FNUMBER": ""
        },
        "FChargeUserId": {
            "FUSERACCOUNT": ""
        },
        "FCustomer": {
            "FNUMBER": ""
        },
        "FApllyDate": "1900-01-01",
        "FCompleteDate": "1900-01-01",
        "FAuditDate": "1900-01-01",
        "FChangeSource": "",
        "FIsStandard": "false",
        "FChangeReason": "",
        "FPriceEx": 0,
        "FApplyOrganization": {
            "FNUMBER": ""
        },
        "FFinishRate": 0,
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
        "FCheckOutDate": "1900-01-01",
        "FEntityAtt": [
            {
                "FEntryID": 0,
                "FAttachObjectIcon": "",
                "FAttachObject": {
                    "FCODE": ""
                },
                "FType": ""
            }
        ],
        "FChangeObjectEntity": [
            {
                "FEntryID": 0,
                "FROWID": "",
                "FPARENTROWID": "",
                "FROWEXPANDTYPE": "",
                "FIsSelect": "false",
                "FBaseObject": 0,
                "FItemType": "",
                "FEntryIcon": "",
                "FObjectCode": "",
                "FObjectName": "",
                "FObjectCategory": {
                    "FName": ""
                },
                "FObjectVerNo": "",
                "FObjectType": "",
                "FModifyReport": "",
                "FIsFinish": "false",
                "FIsSync": "false",
                "FObjectMaxVer": 0,
                "FOBJECTMINVER": 0,
                "FObjectBuildVer": 0,
                "FRefVersionId": 0,
                "FERPBillCode": "",
                "FInventory": "",
                "FDescription": "",
                "FObjectIcon": "",
                "FChangeObject": {
                    "FCODE": ""
                },
                "FSyncErpMode": "",
                "FBatchSubstitutionDetail": [
                    {
                        "FDetailID": 0,
                        "FBS_BOMObject": {
                            "FCODE": ""
                        },
                        "FBS_BomRefVersionId": 0,
                        "FBS_BomNewVersionId": 0
                    }
                ]
            }
        ]
    }
}

五、字段说明：
变更申请单：FBillHead 
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
	 名称：FName 
	 是否拥有权：FIsOwner 
	 拥有人：FOwnerUser 
	 变更对象：FChangeObjectId 
	 是否变更中：FIsChange 
	 是否变更对象：FIsChangeObject 
	 是否是虚文档：FIsVirtualDoc 
	 关联变更单：FECNFormId 
	 创建组织：FCreateOrgId  (必填项)
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
	 变更内容：FRemark 
	 申请人：FApplicant  (必填项)
	 申请部门：FApplyDepartment 
	 客户：FCustomer 
	 申请日期：FApllyDate 
	 变更原因：FChangeReason 
	 申请组织：FApplyOrganization 
	 完成日期：FCompleteDate 
	 审核日期：FAuditDate 
	 变更来源：FChangeSource 
	 负责人：FChargeUserId 
	 完成进度：FFinishRate 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
附件：FEntityAtt 
	 实体主键：FEntryID 
	 文档编码：FAttachObject  (必填项)
	 文档名称：FAttachObjectName 
	 文档图标：FAttachObjectIcon 
	 附件类型：FType 
变更对象：FChangeObjectEntity 
	 实体主键：FEntryID 
	 主键：FROWID 
	 父级内码：FPARENTROWID 
	 行类型：FROWEXPANDTYPE 
	 变更对象标识：FBaseObject 
	 图标：FEntryIcon 
	 对象编码：FObjectCode 
	 对象名称：FObjectName 
	 版本标识：FObjectVerNo 
	 变更项类型：FItemType 
	 修改描述：FDescription 
	 执行描述：FOperation 
	 执行人：FAssign 
	 是否完成：FIsFinish 
	 是否下推同步：FIsSync 
	 主版本号：FObjectMaxVer 
	 次版本号：FOBJECTMINVER 
	 版次号：FObjectBuildVer 
	 变更对象类型：FObjectType 
	 是否选中：FIsSelect 
	 业务类型：FObjectCategory 
	 原版本标识：FRefVersionId 
	 ERP单据编码：FERPBillCode 
	 数量：FInventory 
	 修改报告：FModifyReport 
	 对象图标字符：FObjectIcon 
	 变更对象：FChangeObject 
	 下推方式：FSyncErpMode 
批量替换详情：FBatchSubstitutionDetail 
	 实体主键：FDetailID 
	 BOM对象：FBS_BOMObject 
	 BOM原版本标识：FBS_BomRefVersionId 
	 BOM新版本标识：FBS_BomNewVersionId 

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
client.QueryBusinessInfo("{"FormId":"PLM_PDM_1070100000000000000"}");

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
