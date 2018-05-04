---
title: '&lt;라우팅&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 1771d8a2603a8f61af6ba6e2acf6243d2fd073f7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltroutinggt"></a>&lt;라우팅&gt;

Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다 <xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;**\<라우팅 >**

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
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String" 
               filterName="String" 
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
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
| [**\<필터 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Windows Communication Foundation (WCF) MessageFilter 유형의 들어오는 메시지를 평가할 때 사용될지를 결정 하는 라우팅 필터 집합을 포함 합니다. |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | 필터가 일치할 때 사용할 끝점을 지정하기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함합니다. |

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| **\<시스템입니다. ServiceModel >** | 모든 WCF 구성 요소의 루트 요소입니다. |

## <a name="see-also"></a>참고자료

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
