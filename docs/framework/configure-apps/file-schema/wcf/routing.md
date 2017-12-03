---
title: "&lt;라우팅&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cbe682ef9f7bca25ab4f5089a295ada9a00a8bc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltroutinggt"></a>&lt;라우팅&gt;

들어오는 메시지 및 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의하는 라우팅 테이블을 평가할 때 사용되는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter> 형식을 결정하는 라우팅 필터 집합을 정의하기 위한 구성 섹션을 나타냅니다.

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
| [**\<필터 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | 들어오는 메시지를 평가할 때 사용될 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter 형식을 결정하는 라우팅 필터 집합을 포함합니다. |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | 필터가 일치할 때 사용할 끝점을 지정하기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함합니다. |

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| **\<시스템입니다. ServiceModel >** | 모든 WCF 구성 요소의 루트 요소입니다. |

## <a name="see-also"></a>참고 항목

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
