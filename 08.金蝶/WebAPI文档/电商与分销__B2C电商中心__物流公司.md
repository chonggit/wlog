# 物流公司 Web API 操作原始内容

> 来源页面：全部 > 电商与分销 > B2C电商中心 > 物流公司

## 操作列表

| 操作 | 标识 | 文本长度 |
| --- | --- | ---: |
| 删除 | Delete | 1320 |
| 查看 | View | 1094 |
| 暂存 | Draft | 10629 |
| 保存 | Save | 10628 |
| 提交 | Submit | 1607 |
| 审核 | Audit | 1878 |
| 反审核 | UnAudit | 1765 |
| 禁用 | Forbid | 1689 |
| 反禁用 | Enable | 1689 |
| 撤销 | CancelAssign | 1389 |
| 批量保存 | BatchSave | 3052 |
| 单据查询 | ExecuteBillQuery | 1876 |
| 单据查询(json) | BillQuery | 1861 |
| 元数据查询 | QueryBusinessInfo | 848 |
| 工作流审批 | WorkflowAudit | 1478 |
| 切换组织 | SwitchOrg | 1031 |

## 删除 (`Delete`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.CreateOrgId：创建者组织内码（非必录）
     2.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     2.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     2.4.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Delete("ECC_Transport","{"CreateOrgId":0,"Numbers":[],"Ids":"","NetworkCtrl":""}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "NetworkCtrl": ""
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
client.View("ECC_Transport","{"CreateOrgId":0,"Number":"","Id":"","IsSortBySeq":"false"}");

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

## 暂存 (`Draft`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.NeedUpDateFields：需要更新的字段，数组类型，格式：[key1,key2,...] （非必录）注（更新字段时Model数据包中必须设置内码，若更新单据体字段还需设置分录内码）
     2.2.NeedReturnFields：需返回结果的字段集合，数组类型，格式：[key,entitykey.key,...]（非必录） 注（返回单据体字段格式：entitykey.key）
     2.3.IsDeleteEntry：是否删除已存在的分录，布尔类型，默认true（非必录）
     2.4.SubSystemId：表单所在的子系统内码，字符串类型（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认false（非必录）
     2.6.IsEntryBatchFill：是否批量填充分录，默认true（非必录）
     2.7.ValidateFlag：是否验证数据合法性标志，布尔类型，默认true（非必录）注（设为false时不对数据合法性进行校验）
     2.8.NumberSearch：是否用编码搜索基础资料，布尔类型，默认true（非必录）
     2.9.IsAutoAdjustField：是否自动调整JSON字段顺序，布尔类型，默认false（非必录）
     2.10.InterationFlags：交互标志集合，字符串类型，分号分隔，格式："flag1;flag2;..."（非必录） 例如（允许负库存标识：STK_InvCheckResult）
     2.11.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）
     2.12.IsControlPrecision：是否控制精度，为true时对金额、单价和数量字段进行精度验证，默认false（非必录）
     2.13.ValidateRepeatJson：校验Json数据包是否重复传入，一旦重复传入，接口调用失败，传true则启用校验，传false则不校验（非必录）
     2.14.Model：表单数据包，JSON类型（必录）
备注:
1.示例Model数据包中字段顺序不建议改变，否则可能会有相互影响，如果出现字段值被覆盖或丢失，则可以尝试把字段顺序向后调整一下。
2.示例Model数据包默认包含允许引入的字段，实际按需构建既可。
3.如需创建关联关系，可参考https://club.kingdee.com/forum.php?mod=viewthread&tid=1394265 。
4.对于重要API接口，应设置幂等性校验、设置对应候选键（唯一性字段）的唯一索引等防重调用机制，以防并发导致数据重复。

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""},"Id":"","Number":"","NeedReturnData":[{}]}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Draft("ECC_Transport","{"NeedUpDateFields":[],"NeedReturnFields":[],"IsDeleteEntry":"true","SubSystemId":"","IsVerifyBaseDataField":"false","IsEntryBatchFill":"true","ValidateFlag":"true","NumberSearch":"true","IsAutoAdjustField":"true","InterationFlags":"","IgnoreInterationFlag":"","IsControlPrecision":"false","ValidateRepeatJson":"true","Model":{"FID":0,"FPartnerId":"","FSettlementCurrency":{"FNUMBER":""},"FNumber":"","FSimpleName":"","FName":"","FISPayAfterArrive":"false","FIsDefault":"false","FIsVirtualLogistics":"false","FEnableTBYZ":"false","FFareDefaultWeight":0,"FUseOrgId":{"FNumber":""},"FDescription":"","FCreateOrgId":{"FNumber":""},"FFareDefaultAmount":0,"FFareDefaultNextWeigth":0,"FFareDefaultNextAmount":0,"FLogisticsCode":"","FCODValue1":"","FPayAccountByMonth":"","FKYECustomerKey":"","FClientId":"","FBindBranchName":"","FWeightUnitID":{"FNumber":""},"FCalculationMode":"","FGreater":"","FLess":"","FValue":0,"FGreaterValue":0,"FKYEServiceType":"","FKYEPayType":"","FExpressType":"","FPayMethod":"","FKuaiDi100LogisticsCom":{"FCODE":""},"FEnableJOSAlpha":"false","FEnablePDD":"false","FCNLogisticsCom":{"FCODE":""},"FBranchAccount":{"FCODE":""},"FSHOP":{"FNUMBER":""},"FCloudPrintCode":{"FCODE":""},"FCustomCloudPrint":{"FCODE":""},"FSenderAddressId":{"FNUMBER":""},"FInterfaceVersion":"","FLogisticsFare":[{"FEntryID":0,"FCountryID_F":{"FNUMBER":""},"FRegionId_F":{"FNUMBER":""},"FCityID_F":{"FNUMBER":""},"FCountyID_F":{"FNUMBER":""},"FStreetID_F":{"FNUMBER":""},"FAreaFirstWeight":0,"FAreaFirstAmount":0,"FAreaNextWeight":0,"FAreaNextAmount":0,"FWeightFrom":0,"FWeightTo":0,"FCustomFormula":""}],"FDeliverRegion":[{"FEntryID":0,"FCountryID":{"FNUMBER":""},"FRegionId":{"FNUMBER":""},"FCityID":{"FNUMBER":""},"FCountyID":{"FNUMBER":""},"FStreetID":{"FNUMBER":""}}],"FLogisticsMapEntry":[{"FEntryID":0,"FLogisticsCompany":{"FCode":""},"FShopType":""}],"FShippingTypeEntity":[{"FEntryID":0,"FShoppingTypeID":{"FNUMBER":""}}],"FNetShopScopeEntity":[{"FEntryID":0,"FNetShopId":{"FNUMBER":""},"FIsDefaultLogistics":"false"}],"FMaterialScopeEntity":[{"FEntryID":0,"FMaterialGroupId":{"FNUMBER":""}}]}}");

四、JSON格式数据：
{
    "NeedUpDateFields": [],
    "NeedReturnFields": [],
    "IsDeleteEntry": "true",
    "SubSystemId": "",
    "IsVerifyBaseDataField": "false",
    "IsEntryBatchFill": "true",
    "ValidateFlag": "true",
    "NumberSearch": "true",
    "IsAutoAdjustField": "true",
    "InterationFlags": "",
    "IgnoreInterationFlag": "",
    "IsControlPrecision": "false",
    "ValidateRepeatJson": "true",
    "Model": {
        "FID": 0,
        "FPartnerId": "",
        "FSettlementCurrency": {
            "FNUMBER": ""
        },
        "FNumber": "",
        "FSimpleName": "",
        "FName": "",
        "FISPayAfterArrive": "false",
        "FIsDefault": "false",
        "FIsVirtualLogistics": "false",
        "FEnableTBYZ": "false",
        "FFareDefaultWeight": 0,
        "FUseOrgId": {
            "FNumber": ""
        },
        "FDescription": "",
        "FCreateOrgId": {
            "FNumber": ""
        },
        "FFareDefaultAmount": 0,
        "FFareDefaultNextWeigth": 0,
        "FFareDefaultNextAmount": 0,
        "FLogisticsCode": "",
        "FCODValue1": "",
        "FPayAccountByMonth": "",
        "FKYECustomerKey": "",
        "FClientId": "",
        "FBindBranchName": "",
        "FWeightUnitID": {
            "FNumber": ""
        },
        "FCalculationMode": "",
        "FGreater": "",
        "FLess": "",
        "FValue": 0,
        "FGreaterValue": 0,
        "FKYEServiceType": "",
        "FKYEPayType": "",
        "FExpressType": "",
        "FPayMethod": "",
        "FKuaiDi100LogisticsCom": {
            "FCODE": ""
        },
        "FEnableJOSAlpha": "false",
        "FEnablePDD": "false",
        "FCNLogisticsCom": {
            "FCODE": ""
        },
        "FBranchAccount": {
            "FCODE": ""
        },
        "FSHOP": {
            "FNUMBER": ""
        },
        "FCloudPrintCode": {
            "FCODE": ""
        },
        "FCustomCloudPrint": {
            "FCODE": ""
        },
        "FSenderAddressId": {
            "FNUMBER": ""
        },
        "FInterfaceVersion": "",
        "FLogisticsFare": [
            {
                "FEntryID": 0,
                "FCountryID_F": {
                    "FNUMBER": ""
                },
                "FRegionId_F": {
                    "FNUMBER": ""
                },
                "FCityID_F": {
                    "FNUMBER": ""
                },
                "FCountyID_F": {
                    "FNUMBER": ""
                },
                "FStreetID_F": {
                    "FNUMBER": ""
                },
                "FAreaFirstWeight": 0,
                "FAreaFirstAmount": 0,
                "FAreaNextWeight": 0,
                "FAreaNextAmount": 0,
                "FWeightFrom": 0,
                "FWeightTo": 0,
                "FCustomFormula": ""
            }
        ],
        "FDeliverRegion": [
            {
                "FEntryID": 0,
                "FCountryID": {
                    "FNUMBER": ""
                },
                "FRegionId": {
                    "FNUMBER": ""
                },
                "FCityID": {
                    "FNUMBER": ""
                },
                "FCountyID": {
                    "FNUMBER": ""
                },
                "FStreetID": {
                    "FNUMBER": ""
                }
            }
        ],
        "FLogisticsMapEntry": [
            {
                "FEntryID": 0,
                "FLogisticsCompany": {
                    "FCode": ""
                },
                "FShopType": ""
            }
        ],
        "FShippingTypeEntity": [
            {
                "FEntryID": 0,
                "FShoppingTypeID": {
                    "FNUMBER": ""
                }
            }
        ],
        "FNetShopScopeEntity": [
            {
                "FEntryID": 0,
                "FNetShopId": {
                    "FNUMBER": ""
                },
                "FIsDefaultLogistics": "false"
            }
        ],
        "FMaterialScopeEntity": [
            {
                "FEntryID": 0,
                "FMaterialGroupId": {
                    "FNUMBER": ""
                }
            }
        ]
    }
}

五、字段说明：
单据头：FBillHead 
	 实体主键：FID 
	 单据状态：FDocumentStatus 
	 禁用状态：FForbidStatus 
	 全称：FName 
	 编码：FNumber  (必填项)
	 描述：FDescription 
	 创建组织：FCreateOrgId  (必填项)
	 使用组织：FUseOrgId  (必填项)
	 创建人：FCreatorId 
	 修改人：FModifierId 
	 创建日期：FCreateDate 
	 修改日期：FModifyDate 
	 支持货到付款：FISPayAfterArrive 
	 默认物流公司：FIsDefault 
	 首重：FFareDefaultWeight 
	 首重费用：FFareDefaultAmount 
	 续重：FFareDefaultNextWeigth 
	 续重费用：FFareDefaultNextAmount 
	 结算币别：FSettlementCurrency  (必填项)
	 名称：FSimpleName  (必填项)
	 快递代码：FLogisticsCode  (必填项)
	 电子面单账户：FClientId 
	 电子面单密钥：FPartnerId 
	 虚拟订单默认物流公司：FIsVirtualLogistics 
	 通过菜鸟获取电子面单：FEnableTBYZ 
	 分支网点名称(中通)：FBindBranchName 
	 月结账号(顺丰)：FPayAccountByMonth 
	 重量单位：FWeightUnitID 
	 小数处理模式：FCalculationMode 
	 以实际续重倍数计算续重运费：FRadio 
	 以取整后的续重倍数计算续重运费，取整规则为：小数：FRadio1 
	 大于：FGreater 
	 比较值：FValue 
	 大于比较值：FGreaterValue 
	 付款方式(顺丰)：FPayMethod 
	 快递类型(顺丰)：FExpressType 
	 对应快递100物流公司：FKuaiDi100LogisticsCom 
	 服务类型(跨越物流)：FKYEServiceType 
	 付款方式(跨越物流)：FKYEPayType 
	 客户密钥(跨越物流)：FKYECustomerKey 
	 代收货款卡号：FCODValue1 
	 小于：FLess  (必填项)
	 通过京东阿尔法获取电子面单：FEnableJOSAlpha 
	 接入物流公司：FCNLogisticsCom 
	 网点：FBranchAccount 
	 接入网店：FSHOP 
	 云打印模板：FCloudPrintCode 
	 自定义云打印模板：FCustomCloudPrint 
	 发货地址：FSenderAddressId 
	 通过拼多多云打印获取电子面单：FEnablePDD 
	 接口版本：FInterfaceVersion 
地区运费设置：FLogisticsFare 
	 实体主键：FEntryID 
	 首重：FAreaFirstWeight 
	 首重费用：FAreaFirstAmount 
	 续重：FAreaNextWeight 
	 续重费用：FAreaNextAmount 
	 国家：FCountryID_F  (必填项)
	 省市：FRegionId_F 
	 城市：FCityID_F 
	 区/县：FCountyID_F 
	 街道/乡镇：FStreetID_F 
	 重量范围（从）：FWeightFrom 
	 重量范围（至）：FWeightTo 
	 自定义公式：FCustomFormula  (必填项)
配送区域范围：FDeliverRegion 
	 实体主键：FEntryID 
	 国家：FCountryID 
	 省市：FRegionId 
	 城市：FCityID 
	 区/县：FCountyID 
	 街道/乡镇：FStreetID 
映射关系：FLogisticsMapEntry 
	 实体主键：FEntryID 
	 网店类型：FShopType 
	 平台物流公司代码：FLogisticsCompany 
	 平台物流公司简称：FLogisticsComName 
	 网店：FShopId 
所属物流方式：FShippingTypeEntity 
	 实体主键：FEntryID 
	 物流方式：FShoppingTypeID 
	 物流方式名称：FShoppingTypeName 
配送网店范围：FNetShopScopeEntity 
	 实体主键：FEntryID 
	 网店名称：FNetShopId 
	 网店默认物流公司：FIsDefaultLogistics 
物料配送范围：FMaterialScopeEntity 
	 实体主键：FEntryID 
	 物料组：FMaterialGroupId 

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
     2.1.NeedUpDateFields：需要更新的字段，数组类型，格式：[key1,key2,...] （非必录）注（更新字段时Model数据包中必须设置内码，若更新单据体字段还需设置分录内码）
     2.2.NeedReturnFields：需返回结果的字段集合，数组类型，格式：[key,entitykey.key,...]（非必录） 注（返回单据体字段格式：entitykey.key）
     2.3.IsDeleteEntry：是否删除已存在的分录，布尔类型，默认true（非必录）
     2.4.SubSystemId：表单所在的子系统内码，字符串类型（非必录）
     2.5.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认false（非必录）
     2.6.IsEntryBatchFill：是否批量填充分录，默认true（非必录）
     2.7.ValidateFlag：是否验证数据合法性标志，布尔类型，默认true（非必录）注（设为false时不对数据合法性进行校验）
     2.8.NumberSearch：是否用编码搜索基础资料，布尔类型，默认true（非必录）
     2.9.IsAutoAdjustField：是否自动调整JSON字段顺序，布尔类型，默认false（非必录）
     2.10.InterationFlags：交互标志集合，字符串类型，分号分隔，格式："flag1;flag2;..."（非必录） 例如（允许负库存标识：STK_InvCheckResult）
     2.11.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）
     2.12.IsControlPrecision：是否控制精度，为true时对金额、单价和数量字段进行精度验证，默认false（非必录）
     2.13.ValidateRepeatJson：校验Json数据包是否重复传入，一旦重复传入，接口调用失败，传true则启用校验，传false则不校验（非必录）
     2.14.Model：表单数据包，JSON类型（必录）
备注:
1.示例Model数据包中字段顺序不建议改变，否则可能会有相互影响，如果出现字段值被覆盖或丢失，则可以尝试把字段顺序向后调整一下。
2.示例Model数据包默认包含允许引入的字段，实际按需构建既可。
3.如需创建关联关系，可参考https://club.kingdee.com/forum.php?mod=viewthread&tid=1394265 。
4.对于重要API接口，应设置幂等性校验、设置对应候选键（唯一性字段）的唯一索引等防重调用机制，以防并发导致数据重复。

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""},"Id":"","Number":"","NeedReturnData":[{}]}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Save("ECC_Transport","{"NeedUpDateFields":[],"NeedReturnFields":[],"IsDeleteEntry":"true","SubSystemId":"","IsVerifyBaseDataField":"false","IsEntryBatchFill":"true","ValidateFlag":"true","NumberSearch":"true","IsAutoAdjustField":"true","InterationFlags":"","IgnoreInterationFlag":"","IsControlPrecision":"false","ValidateRepeatJson":"true","Model":{"FID":0,"FPartnerId":"","FSettlementCurrency":{"FNUMBER":""},"FNumber":"","FSimpleName":"","FName":"","FISPayAfterArrive":"false","FIsDefault":"false","FIsVirtualLogistics":"false","FEnableTBYZ":"false","FFareDefaultWeight":0,"FUseOrgId":{"FNumber":""},"FDescription":"","FCreateOrgId":{"FNumber":""},"FFareDefaultAmount":0,"FFareDefaultNextWeigth":0,"FFareDefaultNextAmount":0,"FLogisticsCode":"","FCODValue1":"","FPayAccountByMonth":"","FKYECustomerKey":"","FClientId":"","FBindBranchName":"","FWeightUnitID":{"FNumber":""},"FCalculationMode":"","FGreater":"","FLess":"","FValue":0,"FGreaterValue":0,"FKYEServiceType":"","FKYEPayType":"","FExpressType":"","FPayMethod":"","FKuaiDi100LogisticsCom":{"FCODE":""},"FEnableJOSAlpha":"false","FEnablePDD":"false","FCNLogisticsCom":{"FCODE":""},"FBranchAccount":{"FCODE":""},"FSHOP":{"FNUMBER":""},"FCloudPrintCode":{"FCODE":""},"FCustomCloudPrint":{"FCODE":""},"FSenderAddressId":{"FNUMBER":""},"FInterfaceVersion":"","FLogisticsFare":[{"FEntryID":0,"FCountryID_F":{"FNUMBER":""},"FRegionId_F":{"FNUMBER":""},"FCityID_F":{"FNUMBER":""},"FCountyID_F":{"FNUMBER":""},"FStreetID_F":{"FNUMBER":""},"FAreaFirstWeight":0,"FAreaFirstAmount":0,"FAreaNextWeight":0,"FAreaNextAmount":0,"FWeightFrom":0,"FWeightTo":0,"FCustomFormula":""}],"FDeliverRegion":[{"FEntryID":0,"FCountryID":{"FNUMBER":""},"FRegionId":{"FNUMBER":""},"FCityID":{"FNUMBER":""},"FCountyID":{"FNUMBER":""},"FStreetID":{"FNUMBER":""}}],"FLogisticsMapEntry":[{"FEntryID":0,"FLogisticsCompany":{"FCode":""},"FShopType":""}],"FShippingTypeEntity":[{"FEntryID":0,"FShoppingTypeID":{"FNUMBER":""}}],"FNetShopScopeEntity":[{"FEntryID":0,"FNetShopId":{"FNUMBER":""},"FIsDefaultLogistics":"false"}],"FMaterialScopeEntity":[{"FEntryID":0,"FMaterialGroupId":{"FNUMBER":""}}]}}");

四、JSON格式数据：
{
    "NeedUpDateFields": [],
    "NeedReturnFields": [],
    "IsDeleteEntry": "true",
    "SubSystemId": "",
    "IsVerifyBaseDataField": "false",
    "IsEntryBatchFill": "true",
    "ValidateFlag": "true",
    "NumberSearch": "true",
    "IsAutoAdjustField": "true",
    "InterationFlags": "",
    "IgnoreInterationFlag": "",
    "IsControlPrecision": "false",
    "ValidateRepeatJson": "true",
    "Model": {
        "FID": 0,
        "FPartnerId": "",
        "FSettlementCurrency": {
            "FNUMBER": ""
        },
        "FNumber": "",
        "FSimpleName": "",
        "FName": "",
        "FISPayAfterArrive": "false",
        "FIsDefault": "false",
        "FIsVirtualLogistics": "false",
        "FEnableTBYZ": "false",
        "FFareDefaultWeight": 0,
        "FUseOrgId": {
            "FNumber": ""
        },
        "FDescription": "",
        "FCreateOrgId": {
            "FNumber": ""
        },
        "FFareDefaultAmount": 0,
        "FFareDefaultNextWeigth": 0,
        "FFareDefaultNextAmount": 0,
        "FLogisticsCode": "",
        "FCODValue1": "",
        "FPayAccountByMonth": "",
        "FKYECustomerKey": "",
        "FClientId": "",
        "FBindBranchName": "",
        "FWeightUnitID": {
            "FNumber": ""
        },
        "FCalculationMode": "",
        "FGreater": "",
        "FLess": "",
        "FValue": 0,
        "FGreaterValue": 0,
        "FKYEServiceType": "",
        "FKYEPayType": "",
        "FExpressType": "",
        "FPayMethod": "",
        "FKuaiDi100LogisticsCom": {
            "FCODE": ""
        },
        "FEnableJOSAlpha": "false",
        "FEnablePDD": "false",
        "FCNLogisticsCom": {
            "FCODE": ""
        },
        "FBranchAccount": {
            "FCODE": ""
        },
        "FSHOP": {
            "FNUMBER": ""
        },
        "FCloudPrintCode": {
            "FCODE": ""
        },
        "FCustomCloudPrint": {
            "FCODE": ""
        },
        "FSenderAddressId": {
            "FNUMBER": ""
        },
        "FInterfaceVersion": "",
        "FLogisticsFare": [
            {
                "FEntryID": 0,
                "FCountryID_F": {
                    "FNUMBER": ""
                },
                "FRegionId_F": {
                    "FNUMBER": ""
                },
                "FCityID_F": {
                    "FNUMBER": ""
                },
                "FCountyID_F": {
                    "FNUMBER": ""
                },
                "FStreetID_F": {
                    "FNUMBER": ""
                },
                "FAreaFirstWeight": 0,
                "FAreaFirstAmount": 0,
                "FAreaNextWeight": 0,
                "FAreaNextAmount": 0,
                "FWeightFrom": 0,
                "FWeightTo": 0,
                "FCustomFormula": ""
            }
        ],
        "FDeliverRegion": [
            {
                "FEntryID": 0,
                "FCountryID": {
                    "FNUMBER": ""
                },
                "FRegionId": {
                    "FNUMBER": ""
                },
                "FCityID": {
                    "FNUMBER": ""
                },
                "FCountyID": {
                    "FNUMBER": ""
                },
                "FStreetID": {
                    "FNUMBER": ""
                }
            }
        ],
        "FLogisticsMapEntry": [
            {
                "FEntryID": 0,
                "FLogisticsCompany": {
                    "FCode": ""
                },
                "FShopType": ""
            }
        ],
        "FShippingTypeEntity": [
            {
                "FEntryID": 0,
                "FShoppingTypeID": {
                    "FNUMBER": ""
                }
            }
        ],
        "FNetShopScopeEntity": [
            {
                "FEntryID": 0,
                "FNetShopId": {
                    "FNUMBER": ""
                },
                "FIsDefaultLogistics": "false"
            }
        ],
        "FMaterialScopeEntity": [
            {
                "FEntryID": 0,
                "FMaterialGroupId": {
                    "FNUMBER": ""
                }
            }
        ]
    }
}

五、字段说明：
单据头：FBillHead 
	 实体主键：FID 
	 单据状态：FDocumentStatus 
	 禁用状态：FForbidStatus 
	 全称：FName 
	 编码：FNumber  (必填项)
	 描述：FDescription 
	 创建组织：FCreateOrgId  (必填项)
	 使用组织：FUseOrgId  (必填项)
	 创建人：FCreatorId 
	 修改人：FModifierId 
	 创建日期：FCreateDate 
	 修改日期：FModifyDate 
	 支持货到付款：FISPayAfterArrive 
	 默认物流公司：FIsDefault 
	 首重：FFareDefaultWeight 
	 首重费用：FFareDefaultAmount 
	 续重：FFareDefaultNextWeigth 
	 续重费用：FFareDefaultNextAmount 
	 结算币别：FSettlementCurrency  (必填项)
	 名称：FSimpleName  (必填项)
	 快递代码：FLogisticsCode  (必填项)
	 电子面单账户：FClientId 
	 电子面单密钥：FPartnerId 
	 虚拟订单默认物流公司：FIsVirtualLogistics 
	 通过菜鸟获取电子面单：FEnableTBYZ 
	 分支网点名称(中通)：FBindBranchName 
	 月结账号(顺丰)：FPayAccountByMonth 
	 重量单位：FWeightUnitID 
	 小数处理模式：FCalculationMode 
	 以实际续重倍数计算续重运费：FRadio 
	 以取整后的续重倍数计算续重运费，取整规则为：小数：FRadio1 
	 大于：FGreater 
	 比较值：FValue 
	 大于比较值：FGreaterValue 
	 付款方式(顺丰)：FPayMethod 
	 快递类型(顺丰)：FExpressType 
	 对应快递100物流公司：FKuaiDi100LogisticsCom 
	 服务类型(跨越物流)：FKYEServiceType 
	 付款方式(跨越物流)：FKYEPayType 
	 客户密钥(跨越物流)：FKYECustomerKey 
	 代收货款卡号：FCODValue1 
	 小于：FLess  (必填项)
	 通过京东阿尔法获取电子面单：FEnableJOSAlpha 
	 接入物流公司：FCNLogisticsCom 
	 网点：FBranchAccount 
	 接入网店：FSHOP 
	 云打印模板：FCloudPrintCode 
	 自定义云打印模板：FCustomCloudPrint 
	 发货地址：FSenderAddressId 
	 通过拼多多云打印获取电子面单：FEnablePDD 
	 接口版本：FInterfaceVersion 
地区运费设置：FLogisticsFare 
	 实体主键：FEntryID 
	 首重：FAreaFirstWeight 
	 首重费用：FAreaFirstAmount 
	 续重：FAreaNextWeight 
	 续重费用：FAreaNextAmount 
	 国家：FCountryID_F  (必填项)
	 省市：FRegionId_F 
	 城市：FCityID_F 
	 区/县：FCountyID_F 
	 街道/乡镇：FStreetID_F 
	 重量范围（从）：FWeightFrom 
	 重量范围（至）：FWeightTo 
	 自定义公式：FCustomFormula  (必填项)
配送区域范围：FDeliverRegion 
	 实体主键：FEntryID 
	 国家：FCountryID 
	 省市：FRegionId 
	 城市：FCityID 
	 区/县：FCountyID 
	 街道/乡镇：FStreetID 
映射关系：FLogisticsMapEntry 
	 实体主键：FEntryID 
	 网店类型：FShopType 
	 平台物流公司代码：FLogisticsCompany 
	 平台物流公司简称：FLogisticsComName 
	 网店：FShopId 
所属物流方式：FShippingTypeEntity 
	 实体主键：FEntryID 
	 物流方式：FShoppingTypeID 
	 物流方式名称：FShoppingTypeName 
配送网店范围：FNetShopScopeEntity 
	 实体主键：FEntryID 
	 网店名称：FNetShopId 
	 网店默认物流公司：FIsDefaultLogistics 
物料配送范围：FMaterialScopeEntity 
	 实体主键：FEntryID 
	 物料组：FMaterialGroupId 

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
     2.1.CreateOrgId：创建者组织内码（非必录）
     2.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     2.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     2.4.SelectedPostId：工作流发起员工岗位内码，整型（非必录） 注（员工身兼多岗时不传参默认取第一个岗位）
     2.5.UseOrgId：使用者组织内码（非必录）
     2.6.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）
     2.7.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Submit("ECC_Transport","{"CreateOrgId":0,"Numbers":[],"Ids":"","SelectedPostId":0,"UseOrgId":0,"NetworkCtrl":"","IgnoreInterationFlag":""}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "SelectedPostId": 0,
    "UseOrgId": 0,
    "NetworkCtrl": "",
    "IgnoreInterationFlag": ""
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
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.CreateOrgId：创建者组织内码（非必录）
     2.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     2.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     2.4.InterationFlags：交互标志集合，字符串类型，分号分隔，格式："flag1;flag2;..."（非必录） 例如（允许负库存标识：STK_InvCheckResult）
     2.5.UseOrgId：使用者组织内码（非必录）
     2.6.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）
     2.7.IsVerifyProcInst：是否检验单据关联运行中的工作流实例，布尔类型，默认true（非必录）
     2.8.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）
     2.9.UseBatControlTimes：是否应用单据参数设置分批处理，默认false

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.Audit("ECC_Transport","{"CreateOrgId":0,"Numbers":[],"Ids":"","InterationFlags":"","UseOrgId":0,"NetworkCtrl":"","IsVerifyProcInst":"true","IgnoreInterationFlag":"","UseBatControlTimes":"false"}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "InterationFlags": "",
    "UseOrgId": 0,
    "NetworkCtrl": "",
    "IsVerifyProcInst": "true",
    "IgnoreInterationFlag": "",
    "UseBatControlTimes": "false"
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
client.UnAudit("ECC_Transport","{"CreateOrgId":0,"Numbers":[],"Ids":"","InterationFlags":"","IgnoreInterationFlag":"","UseOrgId":0,"NetworkCtrl":"","IsVerifyProcInst":"true"}");

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

## 禁用 (`Forbid`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.opNumber：操作编码，字符串类型（必录）
3.data：JSON格式数据（详情参考JSON格式数据）（必录）
     3.1.CreateOrgId：创建者组织内码（非必录）
     3.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     3.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     3.4.PkEntryIds：单据内码与分录内码对应关系的集合，字符串类型，格式：[{"Id":"Id1","EntryIds":"EntryId1,EntryId2,..."}] (使用分录状态转换时必录)
     3.5.UseOrgId：使用者组织内码（非必录）
     3.6.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）
     3.7.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.ExcuteOperation("ECC_Transport","Forbid","{"CreateOrgId":0,"Numbers":[],"Ids":"","PkEntryIds":[],"UseOrgId":0,"NetworkCtrl":"","IgnoreInterationFlag":""}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "PkEntryIds": [],
    "UseOrgId": 0,
    "NetworkCtrl": "",
    "IgnoreInterationFlag": ""
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

## 反禁用 (`Enable`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.opNumber：操作编码，字符串类型（必录）
3.data：JSON格式数据（详情参考JSON格式数据）（必录）
     3.1.CreateOrgId：创建者组织内码（非必录）
     3.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     3.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     3.4.PkEntryIds：单据内码与分录内码对应关系的集合，字符串类型，格式：[{"Id":"Id1","EntryIds":"EntryId1,EntryId2,..."}] (使用分录状态转换时必录)
     3.5.UseOrgId：使用者组织内码（非必录）
     3.6.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）
     3.7.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.ExcuteOperation("ECC_Transport","Enable","{"CreateOrgId":0,"Numbers":[],"Ids":"","PkEntryIds":[],"UseOrgId":0,"NetworkCtrl":"","IgnoreInterationFlag":""}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "PkEntryIds": [],
    "UseOrgId": 0,
    "NetworkCtrl": "",
    "IgnoreInterationFlag": ""
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

## 撤销 (`CancelAssign`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.CreateOrgId：创建者组织内码（非必录）
     2.2.Numbers：单据编码集合，数组类型，格式：[No1,No2,...]（使用编码时必录）
     2.3.Ids：单据内码集合，字符串类型，格式："Id1,Id2,..."（使用内码时必录）
     2.4.UseOrgId：使用者组织内码（非必录）
     2.5.NetworkCtrl：是否启用网控，布尔类型，默认false（非必录）

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""}}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.CancelAssign("ECC_Transport","{"CreateOrgId":0,"Numbers":[],"Ids":"","UseOrgId":0,"NetworkCtrl":""}");

四、JSON格式数据：
{
    "CreateOrgId": 0,
    "Numbers": [],
    "Ids": "",
    "UseOrgId": 0,
    "NetworkCtrl": ""
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

## 批量保存 (`BatchSave`)

```text
一、请求参数说明：
1.formid：业务对象表单Id，字符串类型（必录）
2.data：JSON格式数据（详情参考JSON格式数据）（必录）
     2.1.NumberSearch：是否用编码搜索基础资料，布尔类型，默认true（非必录）
     2.2.ValidateFlag：是否验证数据合法性标志，布尔类型，默认true（非必录）注（设为false时不对数据合法性进行校验）
     2.3.IsDeleteEntry：是否删除已存在的分录，布尔类型，默认true（非必录）
     2.4.IsEntryBatchFill：是否批量填充分录，默认true（非必录）
     2.5.NeedUpDateFields：需要更新的字段，数组类型，格式：[key1,key2,...] （非必录）注（更新字段时Model数据包中必须设置内码，若更新单据体字段还需设置分录内码）
     2.6.NeedReturnFields：需返回结果的字段集合，数组类型，格式：[key,entitykey.key,...]（非必录） 注（返回单据体字段格式：entitykey.key）
     2.7.SubSystemId：表单所在的子系统内码，字符串类型（非必录）
     2.8.InterationFlags：交互标志集合，字符串类型，分号分隔，格式："flag1;flag2;..."（非必录） 例如（允许负库存标识：STK_InvCheckResult）
     2.9.Model：表单数据包，JSON类型（必录）
     2.10.BatchCount：服务端开启的线程数，整型（非必录） 注（数据包数应大于此值，否则无效）
     2.11.IsVerifyBaseDataField：是否验证所有的基础资料有效性，布尔类，默认false（非必录）
     2.12.IsAutoAdjustField：是否自动调整JSON字段顺序，布尔类型，默认false（非必录）
     2.13.IgnoreInterationFlag：是否允许忽略交互，布尔类型，默认true（非必录）
     2.14.IsControlPrecision：是否控制精度，为true时对金额、单价和数量字段进行精度验证，默认false（非必录）
     2.15.ValidateRepeatJson：校验Json数据包是否重复传入，一旦重复传入，接口调用失败，传true则启用校验，传false则不校验（非必录）
备注:
1.示例Model数据包中字段顺序不建议改变，否则可能会有相互影响，如果出现字段值被覆盖或丢失，则可以尝试把字段顺序向后调整一下。
2.示例Model数据包默认包含允许引入的字段，实际按需构建既可。
3.如需创建关联关系，可参考https://club.kingdee.com/forum.php?mod=viewthread&tid=1394265 。
4.对于重要API接口，应设置幂等性校验、设置对应候选键（唯一性字段）的唯一索引等防重调用机制，以防并发导致数据重复。

二、返回结果：
{"Result":{"ResponseStatus":{"ErrorCode":"","IsSuccess":"false","Errors":[{"FieldName":"","Message":"","DIndex":0}],"SuccessEntitys":[{"Id":"","Number":"","DIndex":0}],"SuccessMessages":[{"FieldName":"","Message":"","DIndex":0}],"MsgCode":""},"NeedReturnData":[{}]}}

三、代码示例：
// 引用SDK组件Kingdee.BOS.WebApi.Client.dll; SDK下载地址：https://openapi.open.kingdee.com/ApiSdkCenter
var client = new K3CloudApi();
// 初始化登录认证，appID、appSec可在"第三方系统登录授权"中获取
client.InitClient("6871005268bf9d", "appID", "appSec", "userName", 2052, "100", "http://xherp.ipecn.com.cn/k3cloud/");
client.BatchSave("ECC_Transport","{"NumberSearch":"true","ValidateFlag":"true","IsDeleteEntry":"true","IsEntryBatchFill":"true","NeedUpDateFields":[],"NeedReturnFields":[],"SubSystemId":"","InterationFlags":"","Model":[],"BatchCount":0,"IsVerifyBaseDataField":"false","IsAutoAdjustField":"true","IgnoreInterationFlag":"false","IsControlPrecision":"false","ValidateRepeatJson":"true"}");

四、JSON格式数据：
{
    "NumberSearch": "true",
    "ValidateFlag": "true",
    "IsDeleteEntry": "true",
    "IsEntryBatchFill": "true",
    "NeedUpDateFields": [],
    "NeedReturnFields": [],
    "SubSystemId": "",
    "InterationFlags": "",
    "Model": [],
    "BatchCount": 0,
    "IsVerifyBaseDataField": "false",
    "IsAutoAdjustField": "true",
    "IgnoreInterationFlag": "false",
    "IsControlPrecision": "false",
    "ValidateRepeatJson": "true"
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
client.QueryBusinessInfo("{"FormId":"ECC_Transport"}");

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
