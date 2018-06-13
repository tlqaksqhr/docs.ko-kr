---
title: '&lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 31d661f39f9e3de0f7012c7fa52d4964e7ee4a69
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748882"
---
# <a name="ltnamespacetablegt"></a>&lt;namespaceTable&gt;

매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.

**\<system.serviceModel >**   
&nbsp;&nbsp;**\<라우팅 >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**

## <a name="syntax"></a>구문

```xml
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String" prefix="String" />
    </namespaceTable>
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
| [**\<필터 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다. |

### <a name="parent-elements"></a>부모 요소

|     | 설명 |
| --- | ----------- |
| [**\<라우팅 >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 들어오는 메시지를 평가할 및 라우팅 테이블 대상 끝점을 정의 하는 경우에 사용 됩니다 필터가 일치할 때 메시지를 보냅니다. |

## <a name="see-also"></a>참고자료

<xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
