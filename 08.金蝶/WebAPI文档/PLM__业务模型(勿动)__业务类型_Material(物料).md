# 业务类型_Material(物料) Web API 操作原始内容

> 来源页面：全部 > PLM > 业务模型(勿动) > 业务类型_Material(物料)

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 删除对象 | Delete | 9324 |
| 升版 | CreateVersionHistory | 9347 |
| 删除快捷方式 | shortcutDel | 9338 |
| 检入 | OpCheckIn | 9336 |
| 检出 | OpCheckOut | 9337 |
| ERP同步 | ERPSync | 9334 |
| 查看 | View | 1108 |
| 添加快捷方式 | SetShortCut | 9338 |
| 撤销检出 | CancelCheckout | 9341 |
| 打开文件 | OpenFile | 9335 |
| 升大版 | UpgradeBigVersion | 9344 |
| 升小版 | UpgradeSmallVersion | 9346 |
| 保存 | Save | 9320 |
| 新增派生物料 | NewDerivedProduct | 9344 |
| 同步价格 | SynErpPrice | 9338 |
| 下推 | ERPSychronzation | 9343 |
| 提交 | PLMOP_1054_AJ | 9340 |
| 归档 | PLMOP_1054_AC | 9340 |
| 冻结 | PLMOP_1054_AD | 9340 |
| 报废 | PLMOP_1054_AE | 9340 |
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
client.Delete("PLM_PDM_1010000000000000000","Delete","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 升版 (`CreateVersionHistory`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","CreateVersionHistory","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 删除快捷方式 (`shortcutDel`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","shortcutDel","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 检入 (`OpCheckIn`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","OpCheckIn","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 检出 (`OpCheckOut`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","OpCheckOut","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## ERP同步 (`ERPSync`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","ERPSync","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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
client.View("PLM_PDM_1010000000000000000","{"CreateOrgId":0,"Number":"","Id":"","IsSortBySeq":"false"}");

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

## 添加快捷方式 (`SetShortCut`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","SetShortCut","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 撤销检出 (`CancelCheckout`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","CancelCheckout","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 打开文件 (`OpenFile`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","OpenFile","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 升大版 (`UpgradeBigVersion`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","UpgradeBigVersion","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 升小版 (`UpgradeSmallVersion`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","UpgradeSmallVersion","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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
client.Save("PLM_PDM_1010000000000000000","Save","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 新增派生物料 (`NewDerivedProduct`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","NewDerivedProduct","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 同步价格 (`SynErpPrice`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","SynErpPrice","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 下推 (`ERPSychronzation`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","ERPSychronzation","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 提交 (`PLMOP_1054_AJ`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","PLMOP_1054_AJ","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 归档 (`PLMOP_1054_AC`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","PLMOP_1054_AC","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 冻结 (`PLMOP_1054_AD`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","PLMOP_1054_AD","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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

## 报废 (`PLMOP_1054_AE`)

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
client.ExcuteOperation("PLM_PDM_1010000000000000000","PLMOP_1054_AE","{"Parameters":"","Numbers":[],"Ids":"","Model":{"FID":0,"FIcon":"","FBaseObjectNumber":0,"FIsBaseObjectRef":"false","FIsStandard":"false","FIsConvertPBOM":"false","FIsDocCreate":"false","FInStock":0,"FErpTemMaterialID":{"FNUMBER":""},"FDERIVEDSETID":{"FDERIVEDNAME":""},"FMaterialType":"","FBASEUNITID":{"FNUMBER":""},"FMaterialGroup":{"FNUMBER":""},"FPurchaseCycle":0,"FErpMaterialID":{"FNUMBER":""},"FLastCheckinDate":"1900-01-01","FIsChange":"false","FRelationDoc":{"FCODE":""},"FReferPrice":0,"FDERIVEDTYPE":"","FLastCheckin":{"FUserID":""},"FCode":"","FGOODSTYPE":{"FNUMBER":""},"FName":"","FIsSluggish":"false","FNotCreateBom":"false","FIsAssembly":"false","FSpecification":"","FModel":"","FCategoryID":{"FCODE":""},"FErpClsID":"","FCommonType":"","FLifeCircleStage":"","FComponentNum":0,"FCreateDate":"1900-01-01","FCreatorId":{"FUserID":""},"FBATCH":0,"FModifyDate":"1900-01-01","FExtensionMark":"false","FModifierId":{"FUserID":""},"FPROCDEFID":{"FDISPLAYNAME":""},"FBuildVer":0,"FMaxVer":0,"FVerNO":"","FMinVer":0,"FIsCheckOut":"false","FFLOWNUMBER":"","FFolderID":{"FCode":""},"FFLOWSTATUS":"","FFLOWCREATETIME":"1900-01-01","FRemark":"","FFLOWORIGINATORID":{"FUserID":""},"FCheckOutor":{"FUserID":""},"FCbCertification":"false","FBASEOBJECTREF":0,"FIsOwner":"false","FOwnerUser":{"FUserID":""},"FMaxVerNO":"","FInventoryB":{"FINVENTORY":""},"FChangeObjectId":{"FCODE":""},"FMinVerNO":"","FPriceEx":0,"FBOMFLEX":{"FBOMFLEX__FF100001":{"FNumber":""},"FBOMFLEX__FF100002":{"FNumber":""},"FBOMFLEX__FF100003":{"FNumber":""},"FBOMFLEX__FF100005":{"FNumber":""},"FBOMFLEX__FF100010":{"FNumber":""},"FBOMFLEX__FF100007":{"FNumber":""},"FBOMFLEX__FF100008":{"FNumber":""}},"FIsChangeObject":"false","FBOMFlexConfig":{},"FIsFlow":0,"FAllowShare":"false","FIsConvertPDF":"false","FIsConvertHTML":"false","FIsConvertDWG":"false","FSchematicPart":"","FPCBFootprint":"","FTaskTag":"false","FErpPrice":0,"FISINTERNALSAVE":"false","FIsVirtualDoc":"false","FPLMTolerance":"","FECNFormId":{"FCODE":""},"FCreateOrgId":{"FNumber":""},"FGlobalShare":"false","FIdentityKey":"","FVerCreatorId":{"FUserID":""},"FDocFileConfig":{"FCONFIGNAME":""},"FTransUniqueKey":"","FCheckOutDate":"1900-01-01"}}");

四、JSON格式数据：
{
    "Parameters": "",
    "Numbers": [],
    "Ids": "",
    "Model": {
        "FID": 0,
        "FIcon": "",
        "FBaseObjectNumber": 0,
        "FIsBaseObjectRef": "false",
        "FIsStandard": "false",
        "FIsConvertPBOM": "false",
        "FIsDocCreate": "false",
        "FInStock": 0,
        "FErpTemMaterialID": {
            "FNUMBER": ""
        },
        "FDERIVEDSETID": {
            "FDERIVEDNAME": ""
        },
        "FMaterialType": "",
        "FBASEUNITID": {
            "FNUMBER": ""
        },
        "FMaterialGroup": {
            "FNUMBER": ""
        },
        "FPurchaseCycle": 0,
        "FErpMaterialID": {
            "FNUMBER": ""
        },
        "FLastCheckinDate": "1900-01-01",
        "FIsChange": "false",
        "FRelationDoc": {
            "FCODE": ""
        },
        "FReferPrice": 0,
        "FDERIVEDTYPE": "",
        "FLastCheckin": {
            "FUserID": ""
        },
        "FCode": "",
        "FGOODSTYPE": {
            "FNUMBER": ""
        },
        "FName": "",
        "FIsSluggish": "false",
        "FNotCreateBom": "false",
        "FIsAssembly": "false",
        "FSpecification": "",
        "FModel": "",
        "FCategoryID": {
            "FCODE": ""
        },
        "FErpClsID": "",
        "FCommonType": "",
        "FLifeCircleStage": "",
        "FComponentNum": 0,
        "FCreateDate": "1900-01-01",
        "FCreatorId": {
            "FUserID": ""
        },
        "FBATCH": 0,
        "FModifyDate": "1900-01-01",
        "FExtensionMark": "false",
        "FModifierId": {
            "FUserID": ""
        },
        "FPROCDEFID": {
            "FDISPLAYNAME": ""
        },
        "FBuildVer": 0,
        "FMaxVer": 0,
        "FVerNO": "",
        "FMinVer": 0,
        "FIsCheckOut": "false",
        "FFLOWNUMBER": "",
        "FFolderID": {
            "FCode": ""
        },
        "FFLOWSTATUS": "",
        "FFLOWCREATETIME": "1900-01-01",
        "FRemark": "",
        "FFLOWORIGINATORID": {
            "FUserID": ""
        },
        "FCheckOutor": {
            "FUserID": ""
        },
        "FCbCertification": "false",
        "FBASEOBJECTREF": 0,
        "FIsOwner": "false",
        "FOwnerUser": {
            "FUserID": ""
        },
        "FMaxVerNO": "",
        "FInventoryB": {
            "FINVENTORY": ""
        },
        "FChangeObjectId": {
            "FCODE": ""
        },
        "FMinVerNO": "",
        "FPriceEx": 0,
        "FBOMFLEX": {
            "FBOMFLEX__FF100001": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100002": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100003": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100005": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100010": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100007": {
                "FNumber": ""
            },
            "FBOMFLEX__FF100008": {
                "FNumber": ""
            }
        },
        "FIsChangeObject": "false",
        "FBOMFlexConfig": {},
        "FIsFlow": 0,
        "FAllowShare": "false",
        "FIsConvertPDF": "false",
        "FIsConvertHTML": "false",
        "FIsConvertDWG": "false",
        "FSchematicPart": "",
        "FPCBFootprint": "",
        "FTaskTag": "false",
        "FErpPrice": 0,
        "FISINTERNALSAVE": "false",
        "FIsVirtualDoc": "false",
        "FPLMTolerance": "",
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
        "FDocFileConfig": {
            "FCONFIGNAME": ""
        },
        "FTransUniqueKey": "",
        "FCheckOutDate": "1900-01-01"
    }
}

五、字段说明：
物料：FBillHead 
	 实体主键：FID 
	 编码：FCode 
	 创建人：FCreatorId 
	 创建日期：FCreateDate 
	 修改人：FModifierId 
	 修改日期：FModifyDate 
	 业务类型：FCategoryID  (必填项)
	 文件夹：FFolderID 
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
	 ERP物料库存：FInventoryB 
	 物料库存量：FInventoryBP 
	 期初价格：FErpPrice 
	 制造物料：FErpMaterialID 
	 采购周期：FPurchaseCycle 
	 制造物料分组：FMaterialGroup 
	 基本单位：FBASEUNITID 
	 存货类别：FGOODSTYPE 
	 物料种类：FMaterialType  (必填项)
	 派生名称：FDERIVEDSETID 
	 派生类型：FDERIVEDTYPE 
	 组件数量：FComponentNum 
	 制造模板物料：FErpTemMaterialID 
	 是否呆滞料：FIsSluggish 
	 参考价格：FReferPrice 
	 库存：FInStock 
	 是否图纸生成：FIsDocCreate 
	 文档生成物料的文档对象：FRelationDoc 
	 不创建BOM：FNotCreateBom 
	 是否是装配体：FIsAssembly 
	 是否有PBOM：FIsConvertPBOM 
	 任务标记：FTaskTag 
	 对应文档配置：FDocFileConfig 
	 生产方式：FErpClsID 
	 认证状态：FCbCertification 
	 通用级别：FCommonType 
	 备注：FRemark 
	 规格：FSpecification 
	 型号：FModel 
	 公差：FPLMTolerance 
	 原理图图库路径：FSchematicPart 
	 PCB图图形名称：FPCBFootprint 
	 是否标准：FIsStandard 
	 价格：FPriceEx 
	 辅助属性配置：FBOMFlexConfig 
	 辅助属性：FBOMFLEX 
	 描述：FF100001
	 公差：FF100002
	 品牌：FF100003
	 TU归属：FF100005
	 保税非保税：FF100010
	 版本号：FF100007
	 指定对象：FF100008
	 是否有相关对象：FIsBaseObjectRef 
	 相关对象数量：FBaseObjectNumber 
	 是否有DWG：FIsConvertDWG 
	 是否有HTML：FIsConvertHTML 
	 是否有PDF：FIsConvertPDF 

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
client.QueryBusinessInfo("{"FormId":"PLM_PDM_1010000000000000000"}");

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
