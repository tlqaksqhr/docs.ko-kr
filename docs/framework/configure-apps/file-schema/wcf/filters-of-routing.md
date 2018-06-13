---
title: '&lt;routing&gt;의 &lt;filters&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753117"
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;routing&gt;의 &lt;filters&gt;

Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다 <xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 때 사용할 수 있습니다.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;[**\<라우팅 >**](routing.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<필터 >**

## <a name="syntax"></a>구문

```xml
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String" 
              filterData="String" 
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a>특성 및 요소

다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

없음

### <a name="child-elements"></a>자식 요소

|     | 설명 |
| --- | ----------- |
| [**\<필터 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터를 포함<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 때 사용 됩니다. |

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<라우팅 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다. |

## <a name="see-also"></a>참고자료

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
